Lucene Geo-Gazetteer
====================
A command line gazetteer built around the [Geonames.org](http://geonames.org/) 
dataset, that uses the [Apache Lucene](http://lucene.apache.org/) library to 
create a searchable gazetter.


Use
===
[Geonames.org](http://download.geonames.org/export/dump/) Dataset contains over 10,000,000 geographical names corresponding to over 7,500,000 unique features. Beyond names of places in various languages, data stored include latitude, longitude, elevation, population, administrative subdivision and postal codes. All coordinates use the World Geodetic System 1984 (WGS84).

1. What we need here is to download the latest version of allCountries.zip file from GeoNames.org:
`curl -O http://download.geonames.org/export/dump/allCountries.zip`
2. and unzip the GeoNames file:
`unzip allCountries.zip`
3. Take the _allCountries.txt_ and use it to create a geoIndex:
`java -cp target/lucene-geo-gazetteer-<version>-jar-with-dependencies.jar edu.usc.ir.geo.gazetteer.GeoNameResolver -i geoIndex -b allCountries.txt`
4. Then search the index (e.g., for Pasadena and Texas):
`  java -cp target/lucene-geo-gazetteer-<version>-jar-with-dependencies.jar edu.usc.ir.geo.gazetteer.GeoNameResolver -i geoIndex -s Pasadena Texas`

Questions, comments?
===================
Send them to [Chris A. Mattmann](mailto:chris.a.mattmann@jpl.nasa.gov).

Contributors
============
* Yun Li, USC
* Chris A. Mattmann, JPL

License
=======
[Apache License, version 2](http://www.apache.org/licenses/LICENSE-2.0)
