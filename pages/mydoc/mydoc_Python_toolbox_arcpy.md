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

<script src="https://cdnjs.cloudflare.com/ajax/libs/clipboard.js/2.0.8/clipboard.min.js"></script>

<script>
var clipboard = new ClipboardJS('.copy-btn');

clipboard.on('success', function(e) {
    console.info('Texte copié :', e.text);
    e.clearSelection();
});

clipboard.on('error', function(e) {
    console.error('Erreur lors de la copie :', e);
});
</script>



Intepreter path : `C:\Program Files\ArcGIS\Pro\bin\Python\envs\arcgispro-py3\python.exe`

##### Conversion feature table to pandas data frame

<button class="copy-btn" data-clipboard-target="#codeBlock2">Copier</button>
<pre><code id="codeBlock1">
import os
import arcpy
import pandas as pd
from arcgis.features import GeoAccessor, GeoSeriesAccessor

fc_path = os.path.join(gdb_fold, superpos_fc)
sup_dt = pd.DataFrame.spatial.from_featureclass(fc_path)
</code></pre>

##### Webmap


Customize map style with [Arcade expressions](https://github.com/Esri/arcade-expressions) (voir [documentation](https://learn.arcgis.com/fr/paths/try-arcade/))

#### Vérification système de coordonnées

<button class="copy-btn" data-clipboard-target="#codeBlock2">Copier</button>
<pre><code id="codeBlock2">

def print_spatial_ref(path):
    desc = arcpy.Describe(path)
    sr = desc.spatialReference

    if sr.name == "Unknown":
        return {
            "name": "Unknown",
            "factoryCode": None,
            "wkid": None,
            "wkt": None
        }

    return {
        "name": sr.name,
        "factoryCode": sr.factoryCode,
        "wkid": sr.factoryCode,
        "wkt": sr.exportToString()
    }


def compare_spatial_refs(path1, path2):
    sr1 = print_spatial_ref(path1)
    sr2 = print_spatial_ref(path2)

    print("=== Dataset 1 ===")
    print("Path :", path1)
    print("Name :", sr1["name"])
    print("WKID :", sr1["wkid"])

    print("\n=== Dataset 2 ===")
    print("Path :", path2)
    print("Name :", sr2["name"])
    print("WKID :", sr2["wkid"])

    # comparaison stricte par WKID si possible, sinon par WKT
    same = False
    if sr1["wkid"] and sr2["wkid"]:
        same = (sr1["wkid"] == sr2["wkid"])
    else:
        same = (sr1["wkt"] == sr2["wkt"])

    print("\n=== COMPARAISON ===")
    if same:
        print("✔ Les systèmes de coordonnées sont IDENTIQUES")
    else:
        print("❌ Les systèmes de coordonnées sont DIFFÉRENTS")

    return same
 
</code></pre>


#### Copie d'une GDB

<button class="copy-btn" data-clipboard-target="#codeBlock2">Copier</button>
<pre><code id="codeBlock3">
  
import arcpy
import shutil
import os
from datetime import datetime

start_time = datetime.now()


def copy_gdb(src_gdb, dst_gdb):
    """
    Copie une File Geodatabase (.gdb) vers un nouvel emplacement.
    src_gdb : chemin vers la GDB source
    dst_gdb : chemin vers la GDB cible (nouveau dossier .gdb)
    """

    if not os.path.exists(src_gdb):
        raise FileNotFoundError(f"GDB source introuvable : {src_gdb}")

    if os.path.exists(dst_gdb):
        raise FileExistsError(f"La GDB cible existe déjà : {dst_gdb}")

    shutil.copytree(src_gdb, dst_gdb)
    print(f"GDB copiée avec succès :\n{src_gdb}\n→ {dst_gdb}")

    # --- list feature classes ---
    arcpy.env.workspace = dst_gdb

    fcs = arcpy.ListFeatureClasses()
    if not fcs:
        print("Aucune feature class trouvée.")
    else:
        print("Feature classes dans la GDB copiée :")
        for fc in fcs:
            print(" -", fc)


# -----------------------
# Exemple d'utilisation
# -----------------------
src_gdb = r"my_gdb_2.gdb"
dst_gdb = r"my_gdb_2.gdb"

copy_gdb(src_gdb, dst_gdb)

print(f"⏱️{str(start_time)} - {str(datetime.now())}")

 
</code></pre>


  
{% include links.html %}
