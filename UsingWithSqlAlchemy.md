#tricks to use with with sqlalchemy

[SqlAlchemy](http://www.sqlalchemy.org/) doesn't have an engine for pyspatialite, but it does support pysqlite2 - and they both have the exact same interfaces.  To make pyspatialite become the default sqlite engine for [SqlAlchemy](http://www.sqlalchemy.org/), put the following at the top of you main file:
```
import pyspatialite
import sys
sys.modules['pysqlite2'] = pyspatialite
```

From then on, any import of pysqlite2 will actually get pyspatialite!