RESILIENT LINUX SERVER 2.0
==========================

**Resilient Linux Server** is a server operating system based on Debian GNU/Linux which features a liveng partitioning scheme, https://liveng.readthedocs.io, originally thought for live operating systems. Resilient Linux Server, however, is hard drive installable: the liveng compliancy (programs and kernel updates with a readonly system partition) is thus suitable for "indestructible" hard drive installations. Moreover, the persistence partition's rw folder contains the diffs from the stock installation: system backups need a tarball of the rw folder only. 

Here are the instructions on how to build the ISO image, which also contains the installer (https://github.com/marco-buratto/resilientlinux-installer) for creating the liveng partitioning scheme onto disk.


**How to install**

Boot the system with the ISO image, login as *root* / *password* and launch the *resilientlinux-install.sh* script.


**How to build the ISO image**

A **Debian Buster** host is required for the build; other Debian-derived systems may work.

The Resilient Linux ISO image is built using the standard Debian **live-build** framework, so you first need to install it::
 
    apt install -y live-build

Git **clone this project as root**.

In order to build a Resilient Linux Buster-based image, open the terminal emulator **as root**::

    cd /path/to/resilientlinux-server
    lb build

A .iso image will be built according to your host architecture (if building on an amd64, a 64bit iso will be produced; an i386 iso will be built on i386 hosts). We only guarantee the 64bit build to work.
