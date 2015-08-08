#Compiling
Download and build V8, http://code.google.com/p/v8/. Create a shared library (library=shared).

Copy it to /usr/lib/libv8.so.

In your TeaJS directory, type scons. 

This builds the CGI binary, Apache module, MySQL, SQLite, GD and DOM support. You can turn individual components on/off using command-line options. There are many command line options available for building TeaJS; to see a list of them with brief explanation, try scons -Q -h.
Context reusing
This is a new experimental feature, available since rev. 454. If you choose to reuse context, the global JS object will be shared amongst requests. At the beginning of each request, the global object is cleared (all its properties are deleted). This brings a significant performance boost (up to 4x better performance in certain scenarios).

To enable context reusing, compile with reuse_context=1.

##MySQL
Get MySQL development headers (debian: libmysqlclient-dev)
use scons mysql=1
optionally specify MySQL header path with scons mysql=1 mysql_path=/path/to/mysql/libs

##PostgreSQL
Get PostgreSQL development headers (debian: libpq-dev)
use scons pgsql=1
optionally specify PostgreSQL header path with scons pgsql=1 pgsql_path=/path/to/pgsql/libs

##SQLite
Get SQLite3 development headers (debian: libsqlite3-dev)
use scons sqlite=1

##FastCGI
Get FastCGI development headers (debian: libfcgi-dev)
use scons fcgi=1

##GD
Get GD development headers (debian: libgd2-dev)
use scons gd=1

##DOM
Get Xerces-C++ development headers (debian: libxerces-c-dev)
use scons dom=1

##OpenGL
Get glut-dev and libglew-dev development headers (debian: freeglut3-dev, libglew1.5-dev)
use scons gl=1

##Apache module
Get Apache and APR development headers
use scons module=1
optionally specify Apache and APR header path with scons module=1 apache_path=/path/to/apache/libs apr_path=/path/to/apr/libs
