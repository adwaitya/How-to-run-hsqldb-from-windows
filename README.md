# How-to-run-hsqldb-from-windows

In this document, I will show you:
Download software HSQLDB (~ 8MB)
Create example database myDb
Configuring and running HSQLDB.
Download HSQLDB Mar116-19usd-sitewide300X250
http://hsqldb.org/

http://sourceforge.net/projects/hsqldb/files/

-----Windows cmd script to run HSQLDB server and client GUI-------

@echo off
REM set these variables 
SET HSQLDB_HOME=c:\path\to\hsqldb
SET DB_NAME=mydb

REM start the server in new window ( prompt visible, so that you can CTRL+C )

REM database files are created in current directory/data

start java -cp %HSQLDB_HOME%\lib\hsqldb.jar org.hsqldb.server.Server --database.0 file:data/%DB_NAME% --dbname.0 %DB_NAME%

REM start the client GUI and connect to server ( no new cmd window opens because of javaw )

start javaw -cp %HSQLDB_HOME%\lib\hsqldb.jar org.hsqldb.util.DatabaseManagerSwing --url jdbc:hsqldb:hsql://localhost/%DB_NAME%
