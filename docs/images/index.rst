======
Images
======

.. toctree::
   :hidden:

   alpine
   debian
   custom

Flavours
========

The community provides two different base images.
One `Debian <https://debian.org>`_ based and one on `Alpine Linux <https://alpinelinux.org/>`_.

Differnces 
==========

`Debian <https://debian.org>`_ is more known, uses ``apt`` as package manager and standard compilers.

If you already know `Ubuntu <https://ubuntu.com>`_ choose this one.


`Alpine Linux <https://alpinelinux.org/>`_ is a security-oriented, lightweight Linux distribution based on musl libc and busybox.

In general it is smaller than `Debian <https://debian.org>`_ which makes is better as a base image.

Because of ``apk`` as package manager and the use of musl, libc, grsecurity/PaX and Position Independent Executables
it is harder to use.


