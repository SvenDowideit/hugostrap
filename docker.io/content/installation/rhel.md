title
:   Installation on Red Hat Enterprise Linux

description
:   Please note this project is currently under heavy development. It
    should not be used in production.

keywords
:   Docker, Docker documentation, requirements, linux, rhel, centos

# Red Hat Enterprise Linux

Docker is available for **RHEL** on EPEL. These instructions should work
for both RHEL and CentOS. They will likely work for other binary
compatible EL6 distributions as well, but they haven't been tested.

Please note that this package is part of [Extra Packages for Enterprise
Linux (EPEL)][], a community effort to create and maintain additional
packages for the RHEL distribution.

Also note that due to the current Docker limitations, Docker is able to
run only on the **64 bit** architecture.

## Installation

Firstly, you need to install the EPEL repository. Please follow the
[EPEL installation instructions][].

The `docker-io` package provides Docker on EPEL.

If you already have the (unrelated) `docker` package installed, it will
conflict with `docker-io`. There's a [bug report][] filed for it. To
proceed with `docker-io` installation, please remove `docker` first.

Next, let's install the `docker-io` package which will install Docker on
our host.

~~~~ {.sourceCode .bash}
sudo yum -y install docker-io
~~~~

To update the `docker-io` package

~~~~ {.sourceCode .bash}
sudo yum -y update docker-io
~~~~

Now that it's installed, let's start the Docker daemon.

~~~~ {.sourceCode .bash}
sudo service docker start
~~~~

If we want Docker to start at boot, we should also:

~~~~ {.sourceCode .bash}
sudo chkconfig docker on
~~~~

Now let's verify that Docker is working.

~~~~ {.sourceCode .bash}
sudo docker run -i -t fedora /bin/bash
~~~~

**Done!**, now continue with the hello\_world example.

## Issues?

If you have any issues - please report them directly in the [Red Hat
Bugzilla for docker-io component][].

  [Extra Packages for Enterprise Linux (EPEL)]: https://fedoraproject.org/wiki/EPEL
  [EPEL installation instructions]: https://fedoraproject.org/wiki/EPEL#How_can_I_use_these_extra_packages.3F
  [bug report]: https://bugzilla.redhat.com/show_bug.cgi?id=1043676
  [Red Hat Bugzilla for docker-io component]: https://bugzilla.redhat.com/enter_bug.cgi?product=Fedora%20EPEL&component=docker-io
