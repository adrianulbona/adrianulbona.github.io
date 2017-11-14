--- 
layout: post
title: OpenStreetMap in the age of Spark 
---

*Update: [Telenav](https://www.telenav.com) publishes weekly planet Parquet files at [osm-data.skobbler.net](http://osm-data.skobbler.net)*

![My helpful screenshot]({{ site.url }}/assets/2016-12-18-osm-parquetizer.png)

[OpenStreetMap](http://www.openstreetmap.org) is an open/collaborative map considered the Wikipedia of maps. There are tons of information available online and even books about it... anyway, not the history of OSM we will discuss here, but rather we will take a look on the impressive dataset behind and how such a big map can be analysed with modern technologies as [Apache Spark](http://spark.apache.org).  

Short anatomy of the OpenStreetMap
---

One of the reasons OSM got where it is now, is it's quite simple data model. There are only three types of entities: 

- **nodes**: a geo-localized point on the map
- **ways**: roads, building contours, borders (collections of nodes), ...
- **relations**: highways (multiple ways), schools (building contours), ...

Each entity can be tagged (for example, a way tagged with the **highway=residential** marks that the way is a **road** and the road type is **residential**). 

Also meta information about who and when added each entity is kept.

How big the OpenStreetMap actually is?
---

The data is available at <http://planet.openstreetmap.org> and it comes in two formats:

- XML ~ around 53 GB
- PBF ~ around 34 GB

Take a look at [OSMstats](http://osmstats.neis-one.org), if interested on how the map evolves on a daily basis.

Is OpenStreetMap Big Data ready?
---

When I first started to work with OpenStreetMap (mid 2015) I was a bit intrigued to see people waiting hours or even days to get a piece of OSM imported in [PostgreSQL](https://www.postgresql.org) on huge machines. But I said OK ... this is not Big Data. 

Meanwhile, I started to work on various geo-spatial analyses involving technologies from a Big Data stack, where OSM was used and I was again intrigued as the regular way to handle the OSM data was to run [osmosis](https://github.com/openstreetmap/osmosis) over the huge PBF planet file and dump some CSV files for various scenarios. Even if this works, it's suboptimal, and this made me write a converter to [Parquet](https://parquet.apache.org).

The converter is available at [github.com/adrianulbona/osm-parquetizer](https://github.com/adrianulbona/osm-parquetizer). 

Hopefully, this will make the valuable work of so many OSM contributors easily available for the Big Data world.
 
How fast the conversion is?
---------------------------

Less than a minute for [romania-latest.osm.pbf](http://download.geofabrik.de/europe/romania-latest.osm.pbf) and ~3 hours (on a decent laptop with SSD) for the [planet-latest.osm.pbf](http://planet.openstreetmap.org/pbf/planet-latest.osm.pbf).

Demo
---
If you are curious about how these Parquet files look like and how you can query them with Spark SQL, take a look at this [databricks notebook](https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/4082562773728035/2089274675795739/3712305628257488/latest.html).
