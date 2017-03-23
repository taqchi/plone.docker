=============
Custom Images
=============

6. Extending this image
-----------------------
In order to run Plone with your custom theme or Plone Add-ons, you'll have to
build another image based on this one. For this, you'll need to create two files,
`site.cfg` which is a `zc.buildout <https://pypi.python.org/pypi/zc.buildout/2.5.0>`_
configuration file, and `Dockerfile <https://docs.docker.com/engine/reference/builder/>`_
which is the Docker recipe for your image

site.cfg
~~~~~~~~
::

  [buildout]
  extends = buildout.cfg
  eggs +=
    plone.awsome.addon
    plone.other.addon

  [versions]
  plone.awsome.addon = 1.0
  plone.other.addon = 24.13

  # Required by:
  # plone.other.addon = 24.13
  plone.api = 1.5.1


Dockerfile
~~~~~~~~~~
::

  FROM plone:5

  COPY site.cfg /plone/instance/
  RUN bin/buildout -c site.cfg

Build your custom Plone image::

  $ docker build -t custom-plone-image .

Run it::

  $ docker run -p 8080:8080 custom-plone-image
