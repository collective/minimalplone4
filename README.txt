minimalplone4
=============

How to install Plone4 via the minimal buildout configuration
------------------------------------------------------------

* Have Python 2.6 installed, install virtualenv if not done already and
create a Python environment
$ easy_install virtualenv
$ mkdir testplone
$ cd testplone
$ virtualenv --no-site-packages python26

* Get this buildout package via git like so:
$ git clone git://github.com/collective/minimalplone4.git
$ cd minimalplone4

* Bootstrap buildout
$ ../python26/bin/python bootstrap.py -d
$ ./bin/buildout
* Or if you want to use the ZEO configuration:
$ ./bin/buildout -c zeo.cfg

In any case you will be asked for an administrative username and password.

* Fire up Zope and maybe the ZEO Server
$ ./bin/zeoserver start
$ ./bin/instance start

* Point your webbrowser to http://localhost:8080 (username admin,
  password admin) and install a Plone instance.

That's all

More configuration
------------------
If you want to use a differnt port for the servers, you may add some more
onfiguration options, like:

[zeoserver]
zeo-address = 8100

[instance]
http-address = 8080
zeo-address = ${zeoserver:zeo-address}


Author
------
Johannes Raggam <johannes@raggam.co.at>
