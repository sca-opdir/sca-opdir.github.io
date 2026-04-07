---
title: Diverses infos Géodonnées & GeoAI
tags: [geodata, SIG, GeoAI]
last_updated: August 03, 2025
keywords: geodata, SIG
summary: "infos diverses en lien avec les géodonnées, leur analyse et GeoAI"
sidebar: mydoc_sidebar
permalink: geodata_autres_infos.html
folder: mydoc
---

## Ressources en ligne

* [https://book.opengeoai.org/](https://book.opengeoai.org/) official repository for "GeoAI with Python: A Practical Guide to Open-Source Geospatial AI"
* [https://geog-312.gishub.org/](https://geog-312.gishub.org/) official course website for “Introduction to GIS Programming,” offered at the University of Tennessee, Knoxville.

* [https://book.geemap.org](https://book.geemap.org) The book "Earth Engine and Geemap - Geospatial Data Science with Python"

## Packages python

(source : [https://geog-312.gishub.org/book/](https://geog-312.gishub.org/book/))


#### [GeoPandas](https://geopandas.org/)
* extending Pandas data structures
* integrates geospatial operations with a pandas-like interface
* combines the functionalities of Pandas and Shapely
* read/write geodata
* simple accessor methods (.area, .boundary, .centroid, etc.)
* distance calculation
* plotting
* geometric manipulations, e.g. : .buffer(), .convex_hull
* spatial queries and relations, e.g. : .intersects(), .within()
* CRS and reprojection : .crs, .to_crs()

#### [Rasterio](https://rasterio.readthedocs.io/)
* geospatial raster data manipulation
* built on top of GDAL
* reading/writing raster data
* access metadata (.meta), CRS (.crs), resolution (.res), dimension (.width, .height), extent (.bounds), data types (.dtypes)
* affine transformation matrix to map pixel coordinates to geographic coordinate (.transform)
* integrate with matplotlib for raster visualization
* multiple bands manipulation
* band math (e.g. NDVI calculation)
* clipping : raster data with .clip(), vector data with .mask()
* reprojection with rasterio.warp module
* creating raster data from scratch

{% include links.html %}
