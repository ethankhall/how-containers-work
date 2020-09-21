# What is `Docker`?

Docker is made of two things a runtime and an application distribution system.

Docker was first released in 2013.

## Runtime Environment
The runtime environment of Docker is a collection of Linux Kernel features bundeled together into a user-friendly set of comand line tools.

We'll talk about [[Control Groups]] and [[Namespace]] in more detail later.

## Software Distribution
For `docker` to be useful, they needed a distribution mechanism for build tools. Like VM's have `.vdmk` files (disk files), docker has the concept of an image.

At the highest level, an image is a tar file with some json metadata.

We'll talk about them in detail in [[Image]].

## Standardized Tools
Docker was the first set of standardized tools that allowed anyone to use container technology and not just the Google's of the world.

*History:* Google added the basics of containerization into the Linux kernel. The idea of containers is much older from [BSD (2000)](https://en.wikipedia.org/wiki/FreeBSD_jail) and [Solaris (2005)]https://en.wikipedia.org/wiki/Solaris_Containers).