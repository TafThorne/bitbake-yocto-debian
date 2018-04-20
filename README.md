# bitbake-yocto-debian
Docker Image packaging BitBake for use in Yocto builds on-top of The Docker
Official Image for Debian.

The Docker Image is listed on Docker Hub:
https://hub.docker.com/r/tafthorne/bitbake-yocto-debian/

## Using This Image

### Getting The Image

To pull the image:
```
docker pull tafthorne/bitbake-yocto-debian
```

### Intended Use

Yocto requires a certain setup of operating system.  It is not always
conveniant to configure a dedicated host, with a specific version of operating
system and given settings just to perform Yocto builds.  Instead of calling a
nativly installed bitbake command, you can call the version in this tool and
share you work area with it.

For example, if you are presently in the root of your Yocto work area (having
already cloned the neccacary files as discussed in the Yocto Project
Development Manual https://www.yoctoproject.org/docs/2.4.2/dev-manual/dev-manual.html#cloning-the-poky-repository)
you would start a container:
```
docker run -ti --volume=${PWD}:/shared  -w "/shared"s tafthorne/bitbake-yocto-debian
```
initialize the Build Environment within the running container:
```
source oe-init-build-env
```
Build the Image:
```
bitbake core-image-minimal
```

You will then find the image in your host's work area.

## Backgound

### BitBake

BitBake is a make-like tool focused on generating distributions and packages
for cross compiled Linux.  For more details please read:
* https://en.wikipedia.org/wiki/BitBake

It is the main build tool for the Yocto Project.

### Yocto Project

The Yocto Project has a goal of producing tools and processes to enable the
creation of custom Linux distributions for embedded software.  For further
details please read:
* https://en.wikipedia.org/wiki/Yocto_Project
* http://www.yoctoproject.org/

### Debian

Debian is a Linux distribution that's composed entirely of free and open-source
software.

For details about the base image for this project please see either the
project page or the Docker Hub entry.
* https://www.debian.org/intro/about
* https://hub.docker.com/_/debian/

## Contributing

Please see the notes in CONTRIBUTING.md.

