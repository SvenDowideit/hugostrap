title
:   Images

description
:   Definition of an image

keywords
:   containers, lxc, concepts, explanation, image, container

# Image

![image][]

In Docker terminology, a read-only layer\_def is called an **image**. An
image never changes.

Since Docker uses a ufs\_def, the processes think the whole file system
is mounted read-write. But all the changes go to the top-most writeable
layer, and underneath, the original file in the read-only image is
unchanged. Since images don't change, images do not have state.

![image][1]

## Parent Image

![image][2]

Each image may depend on one more image which forms the layer beneath
it. We sometimes say that the lower image is the **parent** of the upper
image.

## Base Image

An image that has no parent is a **base image**.

## Image IDs

All images are identified by a 64 hexadecimal digit string (internally a
256bit value). To simplify their use, a short ID of the first 12
characters can be used on the command line. There is a small possibility
of short id collisions, so the docker server will always return the long
ID.

  [image]: images/docker-filesystems-debian.png
  [1]: images/docker-filesystems-debianrw.png
  [2]: images/docker-filesystems-multilayer.png
