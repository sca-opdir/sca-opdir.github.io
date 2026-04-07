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
Recommended VS Code Extensions
code --install-extension ms-python.python
code --install-extension ms-toolsai.jupyter
code --install-extension charliermarsh.ruff


* [https://geog-312.gishub.org/](https://geog-312.gishub.org/) official course website for “Introduction to GIS Programming,” offered at the University of Tennessee, Knoxville.
revue des principaux packages python (voir plus bas)
  
* [https://book.geemap.org](https://book.geemap.org) The book "Earth Engine and Geemap - Geospatial Data Science with Python"
Python code snippets for :
1. Introducing GEE and Geemap
2. Creating Interactive Maps
3. Using Earth Engine Data
4. Using Local Geospatial Data
5. Visualizing Geospatial Data
6. Analyzing Geospatial Data
7. Exporting Earth Engine Data
8. Making Maps with Cartoee
9. Creating Timelapse Animations
10. Building Interactive Web Apps
11. Earth Engine Applications

[GIS OpenCourseWare](https://courses.gisopencourseware.org/)

* Blog [Cartographie(s) numérique(s)](https://cartonumerique.blogspot.com)

* [Geo-Python](https://geo-python-site.readthedocs.io/en/latest/) : basic concepts of programming and scientific data analysis using the Python programming language

* [pythongis.org](https://pythongis.org/) : online version of the book “Introduction to Python for Geographic Data Analysis”

[5.2. Geographic data in Python](https://pythongis.org/part2/chapter-05/nb/01-introduction-to-geographic-data-in-python.html#)
- vecteurs, rasters, attributs
- les différents formats de fichiers
- GDAL
- bit depth defines the range of distinct values that the raster can store

[5.3. Coordinate reference systems](https://pythongis.org/part2/chapter-05/nb/02-introduction-to-coordinate-reference-systems.html)
 A CRS typically describes the geographic data with three main components: **datum**, **map projection** and **additional parameters**.

Datum: 
- a **model for Earth’s size and shape**, such as a reference ellipsoid or a geoid, which describes the average sea level surface of the Earth ; e.g. World Geodetic System (WGS84)
- contains information about the **origin of the coordinate system**, i.e. the reference point at which the ellipsoid/geoid is tied to a known location on Earth. This is used as a reference for determining the location of other control points that have been precisely measured from the origin.
- includes the **orientation parameters**, which describe the orientation of the coordinate system with respect to the Earth’s surface. They contain information about the tilt of the axis and the position of the origin relative to the Earth’s surface.

Map projection: defines the mathematical transformation used to map the Earth’s surface onto a two-dimensional plane. 

that a CRS can be either 
- **geographic** (=describe positions on the Earth’s surface using latitude and longitude) or
- **projected** (=describe positions on a two-dimensional plane using a Cartesian coordinate system)


[6.1 Representing geographic data in vector format](https://pythongis.org/part2/chapter-06/nb/00-introduction-to-geographic-objects.html)
-> using **shapely**

[6.2 Introduction to geopandas GeoDataFrames](https://pythongis.org/part2/chapter-06/nb/01-geodataframe.html#)
-> geopandas: GeoSeries and GeoDataFrame

[6.3 Common geometric operations](https://pythongis.org/part2/chapter-06/nb/02-geometric-operations.html#)
using geopandas
- .centroid : attribute of GeoDataFrame
- .union_all() : unary union operation combines multiple geometric objects into a single, unified geometric shape ; returns a shapely polygon object out of the results
- .dissolve() : merge geometries, returns a GeoDataFrame as an output
- .envelope : attribute of GeoDataFrame storing bounding polygon (or bounding box or envelope) = smallest rectangular polygon that encloses a given geometry or a set of geometries ; e.g. to get the bounding rectangle for the whole layer : data.union_all().envelope
- .total_bounds : attrribute to fetch coordinates of the bounding box for a GeoDataFrame 
- .bounds : attribute that returns the bounding coordinates of each feature
- .minimum_rotated_rectangle() : rotate around the input geometries and aims to encircle them as tightly as possible
- .minimum_bounding_circle() : creates a circle around the geometries in a way that each geometry is enclosed by the circle
- .convex_hull : attribute of GeoDataFrame ; convex hull represents the smalles possible polygon that contains all points in an object (to get it for full extent : data.union_all().convex_hull)
- concave_hull() : *method* to calculate a concave hull = a polygon that encloses a set of points but, unlike the convex hull (wraps around the outermost points in the tightest convex manner (like a stretched rubber band)), is allowed to have concavities (can bend inward to more closely follow the distribution of the points, providing a boundary that might be more representative of the actual shape of the dataset) ; to return the concave hull for all geometries, need to use dissolve() before to retrieve GeoDataFrame (concave_hull() does not come directly from shapely but is implemented only on geopandas) : data.dissolve().concave_hull() ; more complicated operation, can use various parameters to control the shape of output
 - .simplify() : can also be used to simplify geometries (uses a Douglas-Peucker algorithm to recursively split the original line into smaller parts and connects these parts’ endpoints by a straight line) ; *tolerance* parameter to control the level of simplification
- .buffer() : geometric operation that creates a zone around a given geometry (or geometries), usually representing a certain distance from the shape ; *distance* parameter defines the radius of the buffer (according to data CRS)
- .dissolve() : groups the data based on a specific attribute column and then produces an union of the geometries for each group in that attribute ; dissolve into groups defined by *by* and at the same time aggregating value with *aggfunc*
- .value_counts() from pandas (équivalent R table)

to store the geometric operations into GeoDataFrame : 
- Overwrite the existing geometries in the geometry column by storing the new (manipulated) geometries into it.
- Create a new column to store the new geometries. Then .set_geometry() to activate/set this column as the “active geometry” for your GeoDataFrame (=can have multiple simultaneous columns containing geometries in a GeoDataFrame). However, when saving the geographic data into disk, can in most cases only include 1 column with geometries (except GeoParquet)

## Données
* EE datasets : [browser by tags](https://developers.google.com/earth-engine/datasets/tags?hl=fr)
* [Fields of The World](https://fieldsofthe.world/) (FTW) : comprehensive benchmark dataset designed to enhance the development of machine learning models for instance segmentation of agricultural field boundaries. 





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

#### [Whitebox](https://github.com/jblindsay/whitebox-tools)
* contains over 550 tools for processing many types of geospatial data ; extensive use of parallel computing ; doesn’t need other libraries to be installed ; can be used from scripting environments ; easily plugs into other geographical information system (GIS) software (e.g. can be plugged into QGIS or [ArcGIS](https://github.com/opengeos/WhiteboxTools-ArcGIS))
* [Python](https://github.com/opengeos/whitebox-python) and [R](https://github.com/opengeos/whiteboxR) frontends
* used to perform common GIS and remote sensing analysis tasks
* contains advanced tooling for spatial hydrological analysis and LiDAR data processing
* is not a cartographic or spatial data visualization package; instead it’s meant to serve as an analytical back-end for other data visualization software, like QGIS and ArcGIS

#### [MapLibre](https://github.com/eodaGmbH/py-maplibregl)
* mapping backend in the Leafmap library
* fonctionnalités similaires : build a map from scratch, add controls, and manage different basemap ; 3D building and terrain views, layer customization, and data integration with GeoJSON and raster formats
* cartes dynamiques et interactives

#### [Geemap](https://geemap.org/)
* Google Earth Engine (EE) is a cloud-computing platform that enables scientific analysis and visualization of large-scale geospatial datasets
* geemap package simplifies the use of Google Earth Engine in Python, offering an intuitive API for visualization and analysis in Jupyter notebooks. In Google Colab, geemap is pre-installed
* create interactive maps ; basemaps, layers, inspectors, etc.
* EE Data Catalog can also be searched directly from geemap
* geemap.datasets module to access specific datasets programmatically
* EE objects are server-side entities : stored and processed on Earth Engine’s servers rather than locally
* 5 EE data types : **Image** (= core raster data type, representing single images or scenes) ; **ImageCollection** (= collection or sequence of images, often used for time series analysis) ; **Geometry** (= fundamental vector data type, including shapes like points, lines, and polygons) ; **Feature** (= geometry with associated attributes, used to add descriptive data to vector shapes), **FeatureCollection** (= collection of Features, similar to a shapefile with attribute data)
* raster data is represented as Image objects. Each Image is composed of bands, with each band having its own name, data type, scale, mask, and projection. Metadata for each image is stored as a set of properties.
* ImageCollection represents a sequence of images, often used for temporal data like satellite image time series
* FeatureCollection is a collection of Features. It functions similarly to a GeoJSON FeatureCollection, where features include associated properties or attributes. For example, a shapefile’s data can be represented as a FeatureCollection.
* operations on collection (e.g. filter, aggregate, clip, visualization)
* plotting tool with legends, split-panel maps, linked maps, timeseries inspector, time slider
* vector data : GeoJSON data, shapefiles, GeoDataFrame can be loaded into an EE FeatureCollection (and EE FeatureCollection can be saved into these formats)
* processing of raster data : extract pixel values, zonal statistics, map algebra (e.g. NDVI calculation)
* Single-band and multi-band raster data can be loaded from local files
* Various vector data formats can be loaded and visualized with geemap, including GeoJSON, Shapefile, GeoDataFrame, and GeoPackage formats
* GeoJSON data is styled dynamically with custom colors based on attributes, while Shapefiles and GeoDataFrames allow for simple, structured addition of geographic features to the map.
* easy conversion from CSV files to vector data formats like GeoJSON, Shapefile, and GeoPackage
* add Cloud Optimized GeoTIFF (COG) layers to a map using URLs, which allows for efficient loading and visualization of large raster files stored on the cloud.
* STAC collections can be accessed and visualized similarly, enabling dynamic mapping of spatiotemporal data. By specifying STAC URLs, you can view dataset bounds, center the map on a dataset, and select specific bands to add as layers
* export EE data (images, image collections, timelapse animations) to Google Drive or local drive
* charting EE features (e.g. **feature_by_feature** : feature plotting along the x-axis, with values from selected properties represented along the y-axis (ex. : average monthly temperature across regions, where months serve as series columns) ; **feature.by_property** (ex. : average precipitation by month for each ecoregion ; properties represent precipitation values for each month) ; **feature_groups** : plot groups of features based on property values (ex. : average January temperature for ecoregions divided into “Warm” and “Cold” categories) ; **feature_histogram** (ex. : histogram displaying July precipitation distribution across a region, showing pixel count for different precipitation levels)
* charting EE images : **image_by_region** (ex. monthly temperature for each ecoregion, aggregating data to visualize average temperature by month across regions) ; **image_regions** (ex. : average monthly precipitation across regions, using properties to represent months and comparing precipitation levels) ; **image_by_class** (ex. : spectral signatures of ecoregions by wavelength) ; **image_histogram** (ex. : histograms to visualize MODIS surface reflectance distribution across red, NIR, and SWIR bands)
* charting EE image collections : **image_series** (ex. : time series chart of vegetation indices (NDVI and EVI) for a forest region) ; **image_series_by_region** (ex. : NDVI time series by region, each region has a unique series) ; **image_doy_series** (ex. : average vegetation index by day of year for a specific region) ; **image_doy_series_by_year** (ex. : compares NDVI by doy across 2 different years) ; **image_doy_series_by_region** (ex. : visualize average NDVI by doy across regions)
* Charting Array and List : reduce data to arrays / lists and plot (e.g. scatter plot, transect line plot, metadata scatter plot (e.g. plotting cloud cover against geometric RMSE, useful for quality assessment of image collections), mapped function scatter & line Plot
* chart from a manually created or computed DataTable
* interval chart

##### Key features of geemap
*(source : https://book.geemap.org/chapters/01_introduction.html)*
* Convert Earth Engine JavaScript projects to Python scripts and Jupyter notebooks.
* Display Earth Engine data layers on interactive maps.
* Support Earth Engine JavaScript API-styled functions in Python, such as Map.addLayer(), Map.setCenter(), Map.centerObject(), Map.setOptions().
* Visualize Earth Engine vector and raster data without coding.
* Retrieve Earth Engine data interactively using the Inspector tool.
* Creating interactive plots from Earth Engine data by simply clicking on the map.
* Convert data between the GeoJSON and Earth Engine FeatureCollection formats.
* Use drawing tools to interact with Earth Engine data.
* Use shapefiles with Earth Engine without having to upload data to one’s GEE account.
* Export data in the Earth Engine FeatureCollection format to other formats (i.e., shp, csv, json, kml, kmz).
* Export Earth Engine Image and ImageCollection as GeoTIFF.
* Extract pixels from an Earth Engine Image into a 3D numpy array.
* Calculate zonal statistics by group.
* Add a custom legend for Earth Engine data.
* Convert Earth Engine JavaScript projects to Python code from directly within a Jupyter notebook.
* Add animated text to GIF images generated from Earth Engine data.
* Add colorbar and images to GIF animations generated from Earth Engine data.
* Create satellite timelapse animations with animated text using Earth Engine.
* Search places and datasets from Earth Engine Data Catalog.
* Use the timeseries inspector to visualize landscape changes over time.
* Export Earth Engine maps as HTML files and PNG images.
* Search Earth Engine API documentation within Jupyter notebooks.
* Import Earth Engine assets from personal Earth Engine accounts.
* Publish interactive GEE maps directly within a Jupyter notebook.
* Add local raster datasets (e.g., GeoTIFF) to the map.
* Support Cloud Optimized GeoTIFF (COG) and SpatioTemporal Asset Catalog (STAC).
* Perform image classification and accuracy assessment.
* Extract pixel values interactively and export data as shapefile and CSV.
* Visualize land cover change with Sankey diagrams.
* Load vector data from a PostGIS server.
* Create publication-quality maps with cartoee.


#### [SAMGeo](https://samgeo.gishub.org/)
* Python package for segmenting geospatial data with the Segment Anything Model (SAM)
* automatic mask generation : image segmentation, object annotations
* image_comparison : Compare images with a slider (leafmap)
* image segmentation with input points
* interactive segmentation
* bounding box input prompts
* predict() method to segment the image with specified bounding boxes
* LangSAM class to segment with text prompts


#### [HyperCoast](https://hypercoast.org/)
accessible and comprehensive set of tools for visualizing and analyzing hyperspectral data in coastal environments

#### [DuckDB](https://pypi.org/project/duckdb/)
Python package to connect to a DuckDB database and import data from various formats, including CSV, JSON, DataFrame, parquet, GeoJSON, Shapefile, GeoParquet, and more


## Set up de Visual Studio Code

pour installer les packages sans problème de certificats -> utiliser trusted-host

c:/Users/marzue/AppData/Local/Programs/Python/Python311/python.exe -m pip install ipykernel -U --user --force-reinstall --trusted-host pypi.org --trusted-host files.pythonhosted.org


{% include links.html %}
