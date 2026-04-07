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

#### [Xarray](https://docs.xarray.dev/)
* designed for working with multi-dimensional labeled datasets
* high-level interface for manipulating and analyzing datasets that can be thought of as extensions of NumPy arrays
* valuable for handling multi-dimensional data, especially in scientific applications ; provides metadata, dimension names, and coordinate labels, making it much easier to understand and manipulate data compared to raw NumPy arrays
* particularly useful for geospatial data because it supports labeled axes (dimensions), coordinates, and metadata, making it easier to work with datasets that vary across time, space, and other dimensions.
* 2 main data structures : **DataArray** (=a single multi-dimensional array with labeled dimensions, coordinates, and metadata) and **Dataset** (= a collection of DataArray objects that share the same dimensions and coordinates)  
* DataArray Components are : **Values** (= the actual data stored in a NumPy array or similar structure), **Dimensions** (= named axes of the data (e.g., time, latitude, longitude)), **Coordinates** (= labels for the values in each dimension (e.g., specific times or geographic locations), **Attributes** (= metadata associated with the data (e.g., units, descriptions))
* easily select data based on dimension labels
* intuitive and readable indexing with .()sel (select data based on the labels of coordinates, such as specific times or locations) and .isel() (select data based on the positions of coordinates)
* supports both label-based and position-based indexing
* perform arithmetic operations directly on DataArray objects, similar to how you would with NumPy arrays ; automatic broadcast
* integrates well with Matplotlib and other visualization libraries
* high-level operations that make common computations straightforward, such as .groupby() for calculating statistics, resample, rolling window operations .rolling() (e.g. for smoothing time series data spatially or temporally), and weighted operations with .weighted() (e.g. weight the mean of the dataset by cell area)
* reading/writing files (many common scientific data formats, including netCDF and Zarr)

#### [Rioxarray](https://corteva.github.io/rioxarray/) 
* extension of Xarray that focuses on geospatial raster data
* integration of rasterio’s geospatial data handling capabilities (such as CRS and affine transforms, .crs and .transform())
* ability to load georeferenced raster data, including its CRS and geospatial transformations (e.g.  you can load a raster file (e.g., a GeoTIFF file) directly)
* many accessors, e.g. dimensions with .dims, coordinates with .coords, metadata (including CRS) with .attrs 
* dataset reprojection with .rio.reproject()
* clipping with .rio.clip_box() or .rio.clip()
* rio.resample() to resample the raster dataset to a different resolution 
* .sel() to extract spatial subsets of the dataset by selecting specific coordinate ranges
* visualization with matplotlib
* saving e.g. as GeoTIFF
* handling of nodata values (.rio.set_nodata(), .rio.write_nodata())
* band math to perform computations across different bands (e.g. NDVI calculation)

#### [Leafmap](https://leafmap.org/)
* package for creating, managing, and analyzing interactive geospatial maps ; integrates with Jupyter
* layers, basemaps, XYZ Tile Layers (images pré-générées), WMS Tile Layers (images générées à la demande ; plus flexible, mais plus lent)
* map legends, controls, add markers and marker clusters
* visualization of vector data (polylines, polygons, etc.), GeoPandas GeoDataFrames, GeoParquet Data, Choropleth Maps, PMTiles, Overture Maps Data, raster data (Cloud Optimized GeoTIFFs (COGs), local rasters, multi-band rasters), SpatioTemporal Asset Catalog (STAC),  Data, AWS S3 Integration


{% include links.html %}
