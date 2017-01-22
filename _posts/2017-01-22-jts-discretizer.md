--- 
layout: post
title: A world of hashes ... geo-hashes 
---



The [jts-discretizer](https://github.com/adrianulbona/jts-discretizer) is a tiny Java 8 library able to convert [JTS](https://en.wikipedia.org/wiki/JTS_Topology_Suite) geometries to a set of [GeoHashes](https://en.wikipedia.org/wiki/Geohash) with arbitrary precision (<12). 

A GeoHash-based Mallorca discretization looks like:

![alt tag](https://github.com/adrianulbona/jts-discretizer/raw/master/img/polygon.png)

The smallest geo-hashes are of length 7. Notice that the resulted geo-hash set is optimized, if all children of a certain geo-hash are present in the original set, the children are replaced with the parent.

## How to use it?
```xml
<dependency>
    <groupId>io.github.adrianulbona</groupId>
    <artifactId>jts-discretizer</artifactId>
    <version>0.1.0</version>
</dependency>
```
```java
Geometry geometry = ...
DiscretizerFactory factory = new DiscretizerFactoryImpl();
Set<GeoHash> geoHashes = factory.discretizer(geometry).apply(geometry, 7);
```
