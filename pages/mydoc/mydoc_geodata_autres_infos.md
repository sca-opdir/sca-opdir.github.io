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

TODO : [eo college](https://eo-college.org/)
TODO : [PyGIS](https://pygis.io/docs/a_intro.html) - Open Source Spatial Programming & Remote Sensing
TODO : [python-gis-book](https://python-gis-book.readthedocs.io/en/latest/)
TODO : [Cartographic Visualization in GIS](https://cartogis.readthedocs.io/en/latest/)
TODO : [GEOG 485: GIS Programming and Software Development](https://courses.ems.psu.edu/geog485/node/169)
TODO [https://cartonumerique.blogspot.com](https://cartonumerique.blogspot.com)/
TODO : UZH [EOTutorials](https://github.com/uzh-eoas/EOTutorials)
TODO : GeoAI package [website](https://opengeoai.org/)
TODO : data via Microsoft [Planetary Computer](https://planetarycomputer.microsoft.com/explore?c=30.0586%2C29.9930&z=2.00&v=2)
TODO : [Planet](https://www.planet.com/) data 
TODO : [SXS Training portal](https://www.cs.technik.fhnw.ch/sxs-training-portal/)


* [site](https://gishub.org/) de Qiusheng Wu (TODO : [Linkedin](https://www.linkedin.com/in/giswqs) posts)

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

* Cours du Digital Geography Lab, University of Helsinki
    - [Automating GIS processes I](https://geo-python-site.readthedocs.io/en/latest/) : basic concepts of programming and scientific data analysis using the Python programming language
    - [Automating GIS processes II](https://autogis-site.readthedocs.io/en/latest/course-info/create-python-gis-environment.html) 
    - [Cartographic Visualization in GIS](https://cartogis.readthedocs.io/en/latest/)


## Introduction to Python for Geographic Data Analysis

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


[6.4 Working with map projections](https://pythongis.org/part2/chapter-06/nb/03-coordinate-reference-system.html#)
Changing from one coordinate system to another = map reprojection or coordinate transformation or geographic coordinate conversion ; involves both translation and rotation, and requires knowledge of the shape and size of the Earth, as well as its orientation in space.
- .crs attribute to get current CRS : stores a *CRS* object from the *pyproj* library
- .crs.to_epsg() : to check the current EPSG
- .to_crs() : coordinate transformation of GeoDataFrame with 2 alternative parameters: 1) *crs* (CRS information from various formats, such as proj-strings or OGS WKT text); 2) *epgs* (EPSG-code)

geopandas uses the pyproj.CRS object to store the coordinate reference system information ;  *pyproj* provides many useful functionalities for dealing with CRS information ; use the CRS object/class to easily parse, define and convert CRS information, etc..

- pyproj.CRS.from_epsg(3035) : to initialize a CRS object
- various attributes available from CRS object, e.g. : .name, .coordinate_system, .area_of_use.bounds, .datum
- export CRS information to different formats, e.g. :  .to_wkt(), .to_proj4() and .to_epsg() accordingly

common situations when you need to define a CRS for your data is when creating a new GeoDataFrame from scratch :
- .set_crs(CRS.from_epsg(4326)) on GeoDataFrame or
- .GeoDataFrame(geometry=[Point(24.950899, 60.169158)], crs="EPSG:4326") directly at the creation

global map projections

[6.5 Geocoding](https://pythongis.org/part2/chapter-06/nb/04-geocoding.html#)
= the process of transforming place names or addresses into coordinates (and vice versa)

geopy, geopandas, geocoder -> geocoding based on APIs
- from adress to points : geopandas.tools.geocode()
- reverse geocoding (from list of points / coordinates to address) : geopandas.tools.reverse_geocode()

[6.6 Selecting data based on spatial relationships](https://pythongis.org/part2/chapter-06/nb/05-spatial-queries.html#)

**spatial queries** = specific GIS operations based on how the data layers are located in relation to each other ; conducted based on the **topological spatial relations** (= fundamental constructs that describe how two or more geometric objects relate to each other concerning their position and boundaries)

most GIS software rely on **Dimensionally Extended 9-Intersection Model** (DE-9IM ) 
- = ISO and OGC approved standard ; used to describe and analyze spatial relationships between geometric objects
- defines the topological relations based on the **interior**, **boundary**, and **exterior** of two geometric shapes and how they intersect with each other ; also considers the **dimensionality** of the objects
- under the hood, uses a specific 3x3 intersection matrix to examine the intersections of the interior, boundary and exterior of two geometric objects
- gives a result which is called **spatial predicate** (also called as **binary predicate**), for example : disjoint, contains, within, equals, touches, overlaps, covers (the interior of geometry B is almost totally within A, but they share at least one common coordinate at the border), covered by (geometry A is almost totally contained by the geometry B (except at least one common coordinate at the border) 

all the basic spatial predicates are available from **shapely** library, including:
- .intersects() : the boundary or interior of one object intersect in any way with the boundary or interior of the other object
- .within() 
- .contains()
- .overlaps()
- .touches() : the objects have at least one point in common and their interiors do not intersect with any part of the other object.
- .covers()
- .covered_by()
- .equals()
- .disjoint()
- .crosses()

use **geopandas** to compare the spatial relationships between multiple geometries stored in separate GeoDataFrames
- **.sjoin()** : normally used for conducting a **spatial join** between two spatial datasets (=specific attribute information from a given GeoDataFrame is joined to the other one based on their topological relationship)
- spatial join can be used to conduct spatial queries in geopandas 

selected_points = points.sjoin(selection.geometry.to_frame(), predicate="within")

.geometry.to_frame() : special trick to avoid attaching any extra attributes from the selection geodataframe to our data
-> we are only interested in the geometries of the right-hand-side layer to do the selection, calling the .geometry.to_frame() will first select the geometry column from the selection layer and then converts it into a GeoDataFrame (which would otherwise be a GeoSeries)
-> alternative approach : use selection[[selection.active_geometry_name]], which also returns a GeoDataFrame containing only a column with the geodataframe’s active geometry

!!! whenever making spatial queries is that **both layers need to share the same Coordinate Reference System** for the selection to work properly

.sindex.valid_query_predicates : returns all possible spatial predicates for a given GeoDataFrame

 .sindex = **SpatialIndex** object :
 - prepared automatically by geopandas for GeoDataFrames 
- contains the spatial index for our data = a special data structure that allows for efficient querying of spatial data.
- many different kind of spatial indices, but geopandas uses **R-tree** which is a hierarchical, tree-like structure that divides the space into nested, overlapping rectangles and indexes the bounding boxes of each geometry
- spatial index improves the performance of spatial queries
- .sjoin() method takes advantage of the spatial index -> powerful and faster ; **recommended to use .sjoin()** instead of directly calling .within(), .contains() that come with the shapely geometries

[6.7 Spatial join](https://pythongis.org/part2/chapter-06/nb/06-spatial-join.html#)
e.g. retrieving table attributes from one layer and transferring them into another layer based on their spatial relationship

spatial join is **always conducted between two layers at a time**

**spatial predicates** control how the spatial relationship between the geometries in the two data layers is checked

**spatial join type** : other parameter used to control how the spatial join is conducted ; 
- **inner join** : keep such rows from the right and left tables that have received True after testing the relationship based on the chosen spatial predicate
- **left outer join** : all the rows from the left are kept (no matter what), and the ones from the right that have a match based on spatial predicate will be added to the result
- **right outer join** : the values on the right layer are always kept (no matter what), and only the ones from the left that have a match based on the spatial predicate will be kept

Spatial join can be done easily with geopandas using the **.sjoin()** method ; *predicate* parameter to control the spatial predicate (intersects, overlaps, etc.), and *how* parameter to control the join type (inner, left, right)

!!! 1st step before making a spatial join : check that the **CRS of the layers are identical**

[6.8 Nearest neighbour analysis](https://pythongis.org/part2/chapter-06/nb/07-nearest-neighbour.html#)

various libraries that can be used to find nearest neighbors for given set of geometries, including geopandas, shapely, scipy, scikit-learn, and pysal among others

**.sjoin_nearest()** :
- geopandas method to find nearest neighbors for all geometries in a given GeoDataFrame 
- is actually searching for the closest geometries instead of relying on spatial predicates
- under the hood, the method uses **STRTree** spatial index (an efficient implementation of the R-tree dynamic index structure for spatial searching)
- works with all geometry types
- When using more complex geometries as input (e.g. LineStrings or Polygons), the nearest neighbor search uses spatial index, i.e. it creates bounding boxes around the input geometries and inserts them into an R-Tree which is used to make the search queries more efficient. However, the distance between the nearest neighbours is measured based on the true shapes of the geometric features
- recommended to ensure that 
1) the both GeoDataFrames are having the **same CRS** 
2) preferably having a **projected (metric) CRS** : ensures that the reported distances are meaningful (in meters) and correct.

**K-Nearest Neighbors (KNN) search** : find not only the closest geometry, but a specific number of closest geometries to a given location (1st closest, 2nd closest, and so on).
- also typically built on top of spatial indices to make the queries more efficient
- R-tree implementation in Python only supports finding the closest neighbor (a limitation in the underlying GEOS software)
- use another tree structure called **KD-Tree** (K-dimensional tree) 
- can be conducted using the **scipy** library, after having built the KD-Tree spatial index with **KDTree** method from the scipy.spatial submodule

**nearest neighbors within radius** : 
- can also be done using the KD-Tree spatial index
- build the KDTree index for both datasets and then use a **.query_ball_tree()** method to find all neighbors within the radius *r*

[6.9 Vector overlay operations](https://pythongis.org/part2/chapter-06/nb/08-overlay-analysis-with-vector-data.html#)

- overlays **operate at the GeoDataFrame level**, not on individual geometries, and the properties from both are retained (often, not always)
- for every shape in the left GeoDataFrame, this operation is executed against every other shape in the right GeoDataFrame
- typical vector overlay operations : intersection (=la partie commune à A et B), union (=tout A et tout B), difference (=A sans la partie avec B), symmetric difference(=parties de A ou de B sans leur intersection)
- !!! necessary to ensure that both geographic datasetes share the **same CRS**
- .overlay() method with *how* parameter that control how the overlay analysis is conducted ('intersection', 'union', 'symmetric_difference', 'difference', and 'identity')
- *identity* : geometric intersection of the input features and identity features ; the input features or portions thereof that overlap identity features will get the attributes of those identity features (toutes les entités de A sont conservées ; attributs de B ajoutés si intersection ; à la différence de *sjoin*, les entités de A sont découpées selon les intersections avec B par ex. 1 entité de A peut être découpée en plusieurs morceaux)

(avec *sjoin*, les géométries de départ ne sont pas modifiées, des attributs sont ajoutés ; dans *overlay*, des nouvelles géométries sont créées en combinant les entrées)

[6.10 Data classification](https://pythongis.org/part2/chapter-06/nb/09-data-classification.html#)
= determines the assignment of values to distinct classes

**mapclassify** 
- allows applying various classification schemes on our data that partition the attribute values into mutually exclusive groups
- adequate classification scheme and number of classes depends on the message we want to convey with our map and the underlying distribution of the data
- available classification schemes include: box_plot, equal_interval, fisher_jenks, quantiles, std_mean, etc., etc.
- mapclassify.NaturalBreaks() : tries to split the values into natural clusters
- mapclassify.Quantiles() : splits the data so that each class has an equal number of observations
- mapclassify.PrettyBreaks() : rounds the class break values and divides the range equally to create intervals that look nice and that are easy to read
- mapclassify.UserDefined() : create a custom classification scheme and select which class interval values to use
- combining multiple criteria for classifying data : use pandas skills to combine these rules

[7.1 Representing geographic data in raster format](https://pythongis.org/part2/chapter-07/nb/00-introduction-to-raster-data.html#)

- **xarray** : user-friendly and intuitive way to work with multidimensional raster data with coordinates and attributes (somewhat similar to geopandas that is used for vector data processing)
- **rioxarray** : provides methods to conduct GIS-related operations with raster data (e.g. reading/writing, reprojecting, clipping, resampling)
- **xarray-spatial** : provides methods for analysing raster data (e.g. focal/zonal operations, surface analysis, path finding)
- **geocube** : provides methods for doing data conversions between raster and vector formats (rasterize, vectorize)
- **rasterio** : core library for working with GIS raster data (*rioxarray* is an extension of this library that brings the same functionalities on top of *xarray* library)
- **numpy** : core Python library for numerical computing for representing and working with multidimensional arrays ; has a big influence on how the other raster libraries function and can be used to generate multidimensional arrays from scratch

[7.2 Introduction to data structures in xarray](https://pythongis.org/part2/chapter-07/nb/01-data-structures-xarray.html)

store, combine and analyze all these different layers via a single object, i.e. a **Dataset**.

2 fundamental data structures
1) **DataArray** : a labeled N-dimensional array that is similar to pandas.Series but works with raster data (stored as numpy arrays)
2) **Dataset** : multi-dimensional in-memory array database that contains multiple DataArray objects ; in addition to the variables containing the observations of a given phenomena, you also have the x and y coordinates of the observations stored in separate layers, as well as metadata providing relevant information about your data, such as Coordinate Reference System and/or time ; very similar to geopandas.GeoDataFrame

- .squeeze() to remove a specific dimension
- .rename() to rename data variable(s)
- .plot() on DataArray objects
- .plot.contour() to create contour maps
- .plot.surface() to create surface maps

functionalities to extract basic statistics :
- .max(), .min() ; these functions return DataArray object
- max().item() : add item() to get the xarray.Dataset element as a regular Python scalar value

accessors and methods from rio :
- data.rio.shape, data.rio.width, data.rio.height : get dimensions of the data
- data.rio.resolution()
- data.rio.crs 
- data.rio.transform() : fetch the affine transformation matrix that maps pixel coordinates to geographic coordinates (defines how the raster data is aligned in space, including information on scaling, rotation, and translation relative to a CRS)
- data.rio.bounds() : get the spatial extent
- data\["variable"\].rio.nodata : test whether it contains NaN values
- data\["variable"\].rio.encoded_nodata :  find out what value has been used in the raster file to code the NoData value (in  many cases, the NoData value in a given raster file is actually coded with a specific numerical value that is a clear outlier compared to the rest of the data, such as -9999 or 9999) ; you can also search for the NoData value by checking the *.attrs* attribute that might include information about NoData and is returned as a Python dictionary
- data.dtypes : extract information about the radiometric resolution (i.e. bit depth) ; radiometric resolution is determined by the number of bits used to represent the data for each pixel, which defines the range of possible intensity values
- data.nbytes : information about the memory footprint 
- .astype() : to convert data type (bit depth)

**GeoTIFF** format is one of the most widely used formats to store individual raster layers (i.e. a single DataArray) 

**Cloud Optimized GeoTIFF** (COG) which is a regular GeoTIFF file with an internal organization that enables more efficient workflows on the cloud (can stream just the portion of data that is needed that can significantly reduce processing times and allow working with a single large GeoTIFF file instead of multiple tiles)

**netCDF** : widely used for storing multiple variables into a single file (i.e. a whole xarray.Dataset that can contain multiple variables) ; based on  HDF5

**Zarr** : newer format designed for cloud-native, chunked, and compressed array storage ; allows to write multiple variables (i.e. a whole xarray.Dataset) ; has the ability to store arrays in various ways, including in memory, in files, and in cloud-based object storage (such as Amazon S3 buckets or Google Cloud Storage)

when working with rioxarray and writing data to different file formats, it is useful to **compress** the data : 
- **lossless** compression : file size is reduced without losing or changing any data ; LZW or ZSTD is a good balance between size and speed ; for cloud-based workflows, ZSTD or DEFLATE are good choices for compression
- **lossy** compression : achieves higher compression rate (i.e. smaller file size) with some loss in data quality / precision ; JPEG or JPEG2000

[7.3 Common raster operations](https://pythongis.org/part2/chapter-07/nb/02-common-raster-operations.html#)

**selecting** data :
- .isel() : selecting data by index values
- .sel() : selecting data based on coordinates (with  *x* and *y* parameters)
- .where() : selecting data based on logical conditions

**clipping** raster :
- rio.clip(), for example : use a GeoDataFrame to clip the xarray.Dataset
!!! important that **CRS of both layers are the same** whenever doing GIS operations between multiple layers

**masking** raster : 
mask the data based on certain criteria or using another geographical layer as a mask
- .rio.clip() with *drop=False* and *invert=True* parameters

Creating a **raster mosaic** by merging datasets :
One very common operation when working with raster data is to combine multiple individual raster layers (also called as **tiles**) into a single larger raster dataset, often called as **raster mosaic**
- rioxarray.merge.merge_datasets() : to merge multiple xarray.Datasets together (for merging a list of Dataset objects)

Raster to vector conversion (**vectorize**) :
= convert the data from raster to vector format (**vectorize**) and vice versa (**rasterize**)
- convert a raster *Dataset* to vector format the raster cells are converted into *shapely.Polygon* objects and the values of the cells are stored as an attribute (column) in the resulting *GeoDataFrame*.
- to convert xarray.DataArray into vector format : *geocube* library : geocube.vector.vectorize() => converted the DataArray into vector format and return a GeoDataFrame that contains the geometries of individual cells as shapely.Polygon objects in the geometry column, and the cell values in a column (name of the column automatically added based on the name of the DataArray)
- if similar values close to each other in the raster cells, often good idea to dissolve the geometries based on the data attribute which merges geometries with identical values into single geometries instead of representing all the values as separate polygons with .dissolve() method

Vector to raster conversion (**rasterize**)
- geocube.api.core.make_geocube() to rasterize GeoDataFrame into xarray ; need to specify output CRS and resolution ; to fit the output to have identical resolution to an already existing xarray.Dataset and align it with the other raster layer
use *like* parameter

**Resampling** raster data
= changing the cell values due to changes in the raster grid for example due to changing the effective cell size of an existing dataset. 2 ways :
1) **Upscaling** (or upsampling) = convert the raster to higher resolution, i.e. smaller cells
 - .rio.reproject() method is then used to downscale the data using a new *shape* parameter ; *resampling* parameter to determine the resampling method, provided by rasterio.enums.Resampling class, e.g. *resampling=Resampling.average*
3) **Downscaling** (or downsampling) = resampling (ultimately aggregating) to lower resolution, i.e. having larger cell sizes
- same .rio.reproject() method ; ultimately estimating values to new pixel cells based on the neighboring raster values of a given cell in the input raster ; various methods to interpolate data (e.g. nearest, bilinear, cubic, average, etc.), e.g. *resampling=Resampling.bilinear* determines the value of a new pixel by taking a weighted average of the four nearest input pixels:
- there is no “correct” way to do upscaling as **all resampling methods involve interpolation that introduces uncertainty** to the results. 

Filling **missing data**
- fill with specific predefined values
- .rio.interpolate_na() : predict the values for missing cells based on the neighboring values (**interpolation**) ; different methods available : "nearest" (default), "linear" (slower, based on Delanay triangulation) and "cubic" 

[7.4 Coordinate reference system management](https://pythongis.org/part2/chapter-07/nb/03-coordinate-reference-systems-raster.html#)
2 relevant parts to the georeferencing of a raster dataset:
1) the definition of the local, regional, or global system in which a raster’s pixels are located (CRS), and
2) the parameters by which pixel coordinates are transformed into coordinates in that system.

**Georeferencing** ensures that each pixel corresponds to a specific location on Earth. Central concepts related to georeferencing raster data: 
1) the coordinate reference system (CRS) : defines the **spatial reference** of the raster, specifying how coordinates are measured ; includes a **datum** (e.g. WGS84) and a **projection** (e.g. UTM) that determine how the Earth’s curved surface is represented in a flat raster dataset.
2) the transform : describes how **pixel coordinates (row, column) map to real-world coordinates** (e.g., meters or degrees) ; defines the raster’s **scale**, **rotation**, and **location**
3) the affine : mathematical model commonly used in Python to define the **spatial transformation** of raster data. It consists of **six parameters** that control **translation** (position), **scaling** (resolution), and **rotation** (skew)

- .rio.crs attribute to access CRS information attached to the dataset
- .rio.crs.to_wkt() : to get CRS information in WKT format
- .is_geographic : returns True if the data is in geographic CRS (False otherwise)
- .is_projected : returns True if the data is in projected CRS, e.g. UTM (False otherwise)
- .units_factor : returns information about the units of the coordinates (degree or meter)
- .spatial_ref.attrs : access attributes of the CRS as Python dictionary
- .rio.transform() : access information about affine transformation
- .rio.transform().a : pixel size x-direction
- .rio.transform().e : pixel size y-direction ; scale in y-direction is often reported with **negative** sign which is normal (as **raster images are often stored top-down**).
- .rio.transform().b : rotation/skew x-direction (return the row rotation or skew, which is usually 0 for rasters facing north-up)
- .rio.transform().d : rotation/skew y-direction (return the column rotation or skew, which is usually 0 for rasters facing north-up)
- .rio.transform().c : x-coordinate of the top-left pixel (location of the pixel that is present at index [0, 0] of the 2D array)
- .rio.transform().f : y-coordinate of the top-left pixel (location of the pixel that is present at index [0, 0] of the 2D array)

It is relatively common to use **UTM** coordinate reference system especially when working with raster data that covers large areas on a sub-national level. However, many datasets are typically distributed in **WGS84**, which means that you need to know the UTM zone for a given area that covers the raster dataset before you can reproject the data into metric system. 
- .rio.estimate_utm_crs() : makes it possible to make a sophisticated guess of the UTM-zone that the data falls under. 
!!! if data covers large areas that span across multiple UTM zones, it might not be possible to identify the UTM zone 

(en WGS84 les coordonnées sont en degrés (lat/lon) -> pas pratique pour mesurer des distances/surfaces ; système UTM utilise des mètres, divisé en zones où chaque zone couvre une partie du globe ; pour reprojeter les données WGS84 en UTM il faut déterminer la zone où se trouve le raster ; si un raster couvre plusieurs zones UTM, il n’y a pas de solution parfaite avec UTM)

- .rio.reproject() : transform a dataset from one CRS to another (i.e. **reprojecting**) method ; e.g. using the *dst_crs* parameter that accepts the CRS information as EPSG code, OGC WKT string or Proj4 string

!!! the shape of the raster can change during the CRS transformation : when you reproject raster data to a new coordinate reference system, a few things happen that can change the shape and size of the output raster.
For example : when transforming from geographic WGS84 (CRS that uses degrees) to metric UTM zone 37S (projected CRS in meters), the curved surface of the Earth gets flattened, causing slight distortions. The grid cells, originally evenly spaced in degrees, now stretch and warp in the UTM projection, that can change the dimensions. In addition, the bounding box (extent) of the output raster might shift or expand. When projecting, rioxarray needs to make sure that the grid is properly aligned, so it adjusts the pixel grid to fit the new projection that aims to prevent data loss. These processes are reasons why rioxarray might **add or remove rows/columns to preserve proper alignment when reprojecting data**.
 
[7.5 Map algebra](https://pythongis.org/part2/chapter-07/nb/04-map-algebra.html#)

1) **Focal operations** : compute values based **on a specified neighborhood** (e.g. 3x3 window) on **a** given raster layer.
- any mathematical operator to calculate the pixel values (sum, mean, median, max, min, std, etc.)
- more complex calculations, such as doing edge detection or determining the slope of a terrain 

- xrspatial.**slope**() : calculate slope based on a moving window
- xrspatial.**aspect**() : shows the direction that a slope faces ; measured in degrees from 0° (North) (0=flat areas) to 360° ; helps to determine e.g. sunlight exposure, vegetation patterns, and microclimate conditions
- xrspatial.**curvature**() : how fast the slope is increasing or decreasing as we move along a surface ; positive = the surface is curving up (upwardly convex) ; negative = surface is curving down (downwardly convex) ; 0 = the surface is straight (constant) in whatever angle it is sloped towards
- xrspatial.focal.**hotspots**() : a given pixel has a high value and is surrounded by other high value ; define a *kernel* in order to define the neighborhood (i.e. similar to moving window), that is used to compare values between the given pixel and its surrounding
- xrspatial.**hillshade**() : visualization technique to create a 3D like (2.5D) map based on elevation data ; shadow is generated by blending colors related to the elevation considering the position of the sun, such as 225 degrees of azimuth (direction) and using 25 degrees altitude (angle) over the horizon (calculates an illumination value for each cell)
- xrspatial.focal.focal_stats() : focal statistics that can be used e.g. to **smooth** the surface ; define a kernel (moving window) and then calculate any kind of statistics over it
  
3) **Local operations** : apply functions **on a cell-by-cell basis** between **multiple** raster layers.
- apply any mathematical function
- data classification (**reclassification**) : do not conduct calculations between multiple raster layers per se, but you apply a specific classification criteria or a set of rules for each pixel one-by-one that is used to generate the output raster layer (xrspatial.classify.natural_breaks() followed by xrspatial.classify.reclassify() (par exemple : on veut trouver l'endroit idéal pour construire une maison, on classe sur un score 1-5 les différentes variables chaque couche séparément et ensuite on combine les couches pour avoir un score final pour chaque pixel)
  
4) **Global operations** : use **all raster cells** in computations to calculate e.g. statistical summaries.
- statistical summaries (e.g. .max().item(), etc.)
- xrspatial.**viewshed**() : viewshed analysis = identify areas of a landscape that are visible from a specific location considering the surrounding terrain ; can be calculated based on the elevation data by selecting one or more observer points from where the visibility is analyzed based on the line of sight between the observer and every other cell in the raster ; defined the location and elevation (with .interp()) of the observer
  
5) **Zonal operations** (zonal statistic) : analyze values **within defined zones**, such as calculating average elevation within a watershed.
The fundamental goal of zonal operations is to extract statistical or categorical information about the input value layer.
When the zone layer is a **raster**, each cell value represents a distinct zone ID, and all cells with the same value belong to the same zone.
The zone layer can also be presented in **vector** format as polygons, in which each polygon defines the area that serves as an individual zone (the vector is **internally converted into a raster format** (i.e. rasterized) that aligns with the input value raster in terms of resolution and alignment).
The analysis aggregates the values of the input raster within the spatial boundaries of each zone.

Similarly as with other map algebra operations, you can calculate the mean, sum, minimum, maximum, range, or majority of raster values within each zone. 

!!! Before conducting a zonal operation between the rasters, it is important to **ensure that the CRS is the same** for both layers

- xrspatial.zonal_stats() : zonal statistics with raster zones ; can compute several statistics at once ; returns a pandas.DataFrame that contains the statistics for each zone ; *return_type="xarray.DataArray"* to return the zonal statistics as a DataArray 
- .xvec.zonal_stats() : zonal statistics with vector zones 

7) **Incremental operations** : apply **iterative calculations or cumulative functions** over space or time (e.g. cumulative cost surfaces).
involve multiple stages of calculation based on the input raster in which the calculations are conducted step-by-step

least-cost path calculation based on a raster cost surface :
- example : find an optimal path across a given surface based on the cost of moving from one cell to the other ; treat elevation data as our cost surface and when finding the optimal path across the surface,
- necessary to have a raster that represents the costs
- also common that specific areas cannot be crossed at all (e.g. by providing as a list of values in the cost-raster that cannot be used when finding the optimal path)
- xrspatial.a_star_search() to conduct least-cost path analysis based on raster data ; used **A\* algorithm** based on Euclidean distance

[Introduction to geographic visualization](https://pythongis.org/part2/chapter-08/nb/00-introduction-to-geographic-visualization.html#)

Basic elements of a map : 
- Legend
- Scalebar
- North arrow

Principles of a good map design
- Tufte’s design principles
- Tell a story with data
- Good use of symbols and colors
- Simple style and easy to understand

[8.2 Static maps](https://pythongis.org/part2/chapter-08/nb/01-static-vector-maps.html#)

geopandas GeoDataFrames have a **.plot()** method that can be used to visualize data from wanted columns. In the background, the method uses matplotlib for creating the plots and we can use **matplotlib.pyplot** tools for further customizing our figures

chloropeth map, multi-panel map, add basemap, add layer, crop map extent, etc.

[8.3 Visualizing raster layers](https://pythongis.org/part2/chapter-08/nb/02-static-raster-maps.html)

- plot.show() : function that comes with rasterio
- normalize() to scale band values to range from 0.0 to 1.0
- np.dstack() : stack the values from different values together to produce the RGB true color composite
- plot.show_hist() : look at the histogram of different bands 

[8.4 Interactive maps](https://pythongis.org/part2/chapter-08/nb/03-interactive-maps.html#)

- **folium** makes it easy to visualize geographic data by integrating with Leaflet.js 
- Geopandas.GeoDataFrame.**explore**() uses folium/leaflet.js

change basemap, chloropleth map, etc. more customization with [folium plugins](https://python-visualization.github.io/folium/plugins.html) ; add markers, LayerControl, folium.plugins.HeatMap, folium.plugins.MarkerCluster

9.1 Retrieving OpenStreetMap data

- download with **Osmnx** package (relies on geopandas and another module called networkx)
- ox.geocoder.geocode_to_gdf() : fetch area of interest from place name
- ox.graph.graph_from_place() : retrieve street network
- ox.convert.graph_to_gdfs() : convert the streets (edges of the network) into a GeoDataFrame
- ox.features : module to add features on the map by querying by address: osmnx.features.features_from_address(address, tags, dist) ; bounding box: osmnx.features.features_from_bbox(bbox, tags) ; place: osmnx.features.features_from_place(place, tags) ; point: osmnx.features.features_from_point(center_point, tags, dist) ; polygon: osmnx.features.features_from_polygon(polygon, tags)

[9.2 Retrieving data from Web Feature Service (WFS)](https://pythongis.org/part2/chapter-09/nb/01-retrieving-data-from-wfs.html)

from owslib.wfs import WebFeatureService ; fetch URL then GeoDataFrame.from_features(geojson.loads())

[9.3 Retrieving data from Web Coverage Service (WCS)](https://pythongis.org/part2/chapter-09/nb/02-retrieving-data-from-wcs.html)

[9.4 Reading data from spatial databases](https://pythongis.org/part2/chapter-09/nb/03-read-data-from-spatial-databases.html#)

- read PostGIS database using psycopg2 
- read / write PostGIS database using SqlAlchemy + GeoAlchemy
- read / write Spatialite database

## [Automating GIS processes II](https://autogis-site.readthedocs.io/)

[Shapely and geometry objects](https://autogis-site.readthedocs.io/en/latest/lessons/lesson-1/geometry-objects.html#)

LineString geometries (and the related LinearRings) represent lines. They are defined by a sequence of points

A polygon is defined by exactly one LinearRing as its circumference, and any number of additional LinearRings representing holes that are cut out.

MultiPoint geometries represent collections of points.

MultiLineString geometries represent collections of lines.

MultiPolygon geometries represent collections of polygons.

GeometryCollection geometries are collections of points, lines, and polygons, as well as multi-points, multi-lines, and multi-polygons

each geometry types has many properties and methods associated

Shapely geometries are, by design, agnostic (unaware) of the reference system used to represent them. Distances and surface area calculated using the built-in shapely methods will always:
- assume a flat, Cartesian, Euclidean space, and
- return the calculated value in the unit of the coordinates (e.g., meters, or degrees).

 shapely.geometry.box() : short-hand function to create rectangular polygons

- .convex_hull : ‘convex hull’ refers to the smallest possible convex polygon that can contain a geometry or a set of geometries.
- .envelope : smallest rectangular polygon around a geometry/set of geometries
- .is_valid : built-in check that requirements of geometric primitives are met (e.g. a LineString must consist of at least two points, and a Polygon’s exterior shell and holes must not intersect)

[Vector data I/O](https://autogis-site.readthedocs.io/en/latest/lessons/lesson-2/vector-data-io.html#)  

**fiona** allows very low-level access to geodata files

most commonly used higher-level library for geospatial vector data is **geopandas**

[Geopandas : an introduction](https://autogis-site.readthedocs.io/en/latest/lessons/lesson-2/geopandas-an-introduction.html#)

geometries in a GeoDataFrame are stored as *shapely* objects

geopandas builds on top of *pandas*, and it inherits most of its functionality

Both *GeoSeries* (geometry columns) and *GeoDataFrames* have an **area** property

[Map projections](https://autogis-site.readthedocs.io/en/latest/lessons/lesson-2/map-projections.html#)

Without a **coordinate reference systems** (CRS), the geometries would simply be a collection of coordinates in an arbitrary space. Only the CRS allows GIS software to relate these coordinates to a place on Earth

**Map projections**, also called **projected** coordinate systems, are mathematical models that allow us to transfer coordinates on the surface of our three-dimensional Earth into coordinates in a planar surface

**geographic** coordinate systems simply directly use latitude and longitude, i.e. the degrees along the horizontal and vertical great circles of a sphere approximating the Earth, as the x and y coordinates in a planar map. 

there are both projected and geographic coordinate systems that make use of more complex ellipsoids than a simple sphere to better approximate the ‘potato-shaped’ reality of our planet

full CRS information needed to accurately relate geospatial information to a place on Earth includes both (projected/geographic) **coordinate system** and **ellipsoid**.

coordinate systems are optimised for certain regions and purposes. No coordinate system can be perfectly accurate around the globe, and the transformation from three- to two-dimensional coordinates can not be accurate in *angles*, *distances*, and *areas* simultaneously.

ESRI Shapefile format consist of multiple files with different file extensions. The .prj file contains information about the coordinate reference system

EPSG code is 4326. This is number to remember, as you will come across it a lot in the geospatial world: It refers to a geographic coordinate system using the WGS-84 reference ellipsoid. This is the most commonly used coordinate reference system in the world. It’s what we refer to when we speak of longitude and latitude.

**pyproj** module for handling CRS

[Geocoding](https://autogis-site.readthedocs.io/en/latest/lessons/lesson-3/geocoding.html)
converting addresses into coordinates and vice versa, i.e. geocoding

geocoding with **geopy** and **geocoder** ; access geocoding services via APIs

**Nominatim** is a library and service using OpenStreetMap data, and run by the OpenStreetMap Foundation

.merge() vs .join()
- .merge() : based on common attributes (more flexible) ; useful for spatial joins when you want to match features based on attribute values in specific columns rather than just the index
- .join() : based on their index (need to have same number of records and share the same index (same order of rows)) ; works similarly to a SQL join based on the index of the two tables ; ideal for adding columns from one GeoDataFrame to another based on the index or a pre-aligned structure


[Point-in-polygon queries](https://autogis-site.readthedocs.io/en/latest/lessons/lesson-3/point-in-polygon-queries.html#)

detecting if a point is inside a polygon is most commonly done using a specific formula called **Ray Casting algorithm** (straight line extended from the point in question to infinity in one direction ; count how many times it intersects with the edges of the polygon ; even number : the point is outside ; odd count : point is inside)

in practice : **shapely’s binary predicates** that can evaluate the topolocical relationships between geographical objects
- within() : checks if a point is within a polygon
- contains() : checks if a polygon contains a point
also work on geopandas.GeoDataFrame (returns whether or not a row’s geometry is contained in the supplied other geometry) ; for ex. : within() against a column is carried out row-wise: the first address point would be checked against the first polygon, the second address point against the second polygon, and so forth


[Intersect](https://autogis-site.readthedocs.io/en/latest/lessons/lesson-3/intersect.html)

implemented in shapely
- intersects():  the boundary or interior of one object intersect in any way with the boundary or interior of the other object.
- touches(): at least one point in common, but their interiors do not intersect with any part of the other object.


[Spatial join](https://autogis-site.readthedocs.io/en/latest/lessons/lesson-3/spatial-join.html)
= operation that combines data from two or more spatial data sets based on their geometric relationship

require two input parameters: 
1) the **predicate**, i.e., the *geometric condition* that needs to be met between two geometries (intersects, contains, within, touches, crosses, overlaps)
2) the **join-type**: whether only rows with matching geometries are kept, or all of one input table’s rows, or all records (left, right, inner)

shapely supports more binary geometric predicates than those geopandas implements for spatial joins
 
## Données
* EE datasets : [browser by tags](https://developers.google.com/earth-engine/datasets/tags?hl=fr)
* [Fields of The World](https://fieldsofthe.world/) (FTW) : comprehensive benchmark dataset designed to enhance the development of machine learning models for instance segmentation of agricultural field boundaries. 
* [Natural Earth Data](https://www.naturalearthdata.co)

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
