# catproject





# Install GeoDjango
    django-admin startproject cat
    cd cat
    python manage.py startapp exposure
    python manage.py startapp levee
    createdb geo
    createdb tmp
    psql 
    CREATE ROLE geo WITH LOGIN PASSWORD 'geo';
    GRANT ALL PRIVILEGES ON DATABASE tmp TO geo;
    GRANT ALL PRIVILEGES ON DATABASE geo TO geo;
    ALTER USER geo CREATEDB;
    psql geo
    ALTER USER geo WITH PASSWORD 'geo';
    CREATE EXTENSION postgis;

## Setting up the admin and shit
Make Migrations
    python manage.py makemigrations

#### Interactive migration
Set up the django admin shell
     python manage.py shell



# OGR and Fiona Reference

you can read a zipped geodatabase like so:
ogrinfo /vsizip/Trecks.gdb.zip/Trecks.gdb [*](https://gis.stackexchange.com/questions/143577/how-to-read-esri-file-geodatabase-filegdb-with-ogr)

postgis connection string: 
    PG:"dbname='databasename' host='addr' port='5432' user='x' password='y'"

Ogrinfo [*](https://trac.osgeo.org/postgis/wiki/UsersWikiOGR)
    ogrinfo -ro PG:dbname=warmerda -sql "SELECT pop_1994 from canada where province_name = 'Alberta'"


# Raster Reference
Really good foss4geo 2015 write up [here](ftp://ftp.remotesensing.org/gdal/workshop/foss4ge2015/workshop_gdal.html)