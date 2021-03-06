minimalplone4
=============

This is a minimal buildout configuration for installing the latest Plone 4.


Prerequisites
-------------
- Python 2.6 or Python 2.7
- Python virtualenv
- Git


Install
-------

::

    $ git clone git@github.com:collective/minimalplone4.git
    $ cd minimalplone4
    $ virtualenv . -p python # Make sure, it's installing Python 2.6 or 2.7, change 'python' to your python 2 location if needed
    $ ./bin/pip install -r requirements.txt
    $ ./bin/buildout

- Or if you want to use the ZEO configuration::

    $ ./bin/buildout -c zeo.cfg

- Fire up Zope and maybe the ZEO Server::

    $ ./bin/zeoserver start
    $ ./bin/instance start

- Point your webbrowser to http://localhost:8080 (username admin, password
  admin) and install a Plone instance.

That's all


Extend the config
-----------------

For your own projects, you might extend the configuration. Use a different
PORT, add some more eggs, like::

    [zeoserver]
    zeo-address = 8100

    [instance]
    http-address = 8080
    zeo-address = ${zeoserver:zeo-address}
    eggs +=
        plone.app.debugtoolbar
        plone.app.widgets
