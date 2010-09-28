How to install Plone4 via the minimal buildout configuration
============================================================

* Have Python 2.6 installed

* Get this buildout package via git like so:
$ git clone git://github.com/collective/minimalplone4.git

* Point your terminal to the minimalplone4 directory
$ cd minimalplone4

* Do:
$ python bootstrap.py -d
$ ./bin/buildout
* Or if you want to use the ZEO configuration:
$ ./bin/buildout -c zeo.cfg

* Fire up Zope and maybe the ZEO Server
$ ./bin/zeoserver start
$ ./bin/instance start

* Point your webbrowser to http://localhost:8080 (username admin,
  password admin) and install Plone

That's all

Author
------
Johannes Raggam <johannes@raggam.co.at>
