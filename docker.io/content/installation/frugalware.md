title
:   Installation on FrugalWare

description
:   Please note this project is currently under heavy development. It
    should not be used in production.

keywords
:   frugalware linux, virtualization, docker, documentation,
    installation

# FrugalWare

Installing on FrugalWare is handled via the official packages:

-   [lxc-docker i686][]
-   [lxc-docker x86\_64][]

The lxc-docker package will install the latest tagged version of Docker.

## Dependencies

Docker depends on several packages which are specified as dependencies
in the packages. The core dependencies are:

-   systemd
-   lvm2
-   sqlite3
-   libguestfs
-   lxc
-   iproute2
-   bridge-utils

## Installation

A simple :

    pacman -S lxc-docker

is all that is needed.

## Starting Docker

There is a systemd service unit created for Docker. To start Docker as
service:

    sudo systemctl start lxc-docker

To start on system boot:

    sudo systemctl enable lxc-docker

  [lxc-docker i686]: http://www.frugalware.org/packages/200141
  [lxc-docker x86\_64]: http://www.frugalware.org/packages/200130
