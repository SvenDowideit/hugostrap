title
:   Installation on Google Cloud Platform

description
:   Please note this project is currently under heavy development. It
    should not be used in production.

keywords
:   Docker, Docker documentation, installation, google, Google Compute
    Engine, Google Cloud Platform

# [Google Cloud Platform][]

## [Compute Engine][] QuickStart for [Debian][]

1.  Go to [Google Cloud Console][] and create a new Cloud Project with
    [Compute Engine enabled][].
2.  Download and configure the [Google Cloud SDK][] to use your project
    with the following commands:

~~~~ {.sourceCode .bash}
$ curl https://dl.google.com/dl/cloudsdk/release/install_google_cloud_sdk.bash | bash
$ gcloud auth login
Enter a cloud project id (or leave blank to not set): <google-cloud-project-id>
~~~~

3.  Start a new instance, select a zone close to you and the desired
    instance size:

~~~~ {.sourceCode .bash}
$ gcutil addinstance docker-playground --image=backports-debian-7
1: europe-west1-a
...
4: us-central1-b
>>> <zone-index>
1: machineTypes/n1-standard-1
...
12: machineTypes/g1-small
>>> <machine-type-index>
~~~~

4.  Connect to the instance using SSH:

~~~~ {.sourceCode .bash}
$ gcutil ssh docker-playground
docker-playground:~$ 
~~~~

5.  Install the latest Docker release and configure it to start when the
    instance boots:

~~~~ {.sourceCode .bash}
docker-playground:~$ curl get.docker.io | bash
docker-playground:~$ sudo update-rc.d docker defaults
~~~~

6.  Start a new container:

~~~~ {.sourceCode .bash}
docker-playground:~$ sudo docker run busybox echo 'docker on GCE \o/'
docker on GCE \o/
~~~~

  [Google Cloud Platform]: https://cloud.google.com/
  [Compute Engine]: https://developers.google.com/compute
  [Debian]: https://www.debian.org
  [Google Cloud Console]: https://cloud.google.com/console
  [Compute Engine enabled]: https://developers.google.com/compute/docs/signup
  [Google Cloud SDK]: https://developers.google.com/cloud/sdk/
