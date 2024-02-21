---
title: Python snippets
tags: [Python, programming]
last_updated: February 21, 2024
keywords: Python, programming
summary: "codes Arcpy et Python toolbox"
sidebar: mydoc_sidebar
permalink: Python_toolbox_arcpy.html
folder: mydoc
---

{% include note.html content="Ne sont pas disponibles en lignes, usage offline uniquement" %}


Intepreter path : `C:\Program Files\ArcGIS\Pro\bin\Python\envs\arcgispro-py3\python.exe`

##### Conversion feature table to pandas data frame

```{Python}
import os
import arcpy
import pandas as pd
from arcgis.features import GeoAccessor, GeoSeriesAccessor

fc_path = os.path.join(gdb_fold, superpos_fc)
sup_dt = pd.DataFrame.spatial.from_featureclass(fc_path)

```



{% include links.html %}
