---
title: Diverses infos FME
tags: [FME, SIG]
last_updated: June 12, 2025
keywords: FME, SIG
summary: "infos diverses sur FME"
sidebar: mydoc_sidebar
permalink: FME_autres_infos.html
folder: mydoc
---

10 conseils pour gagner en productivité avec FME
1 – « Ce que l’on conçoit bien s’exprime clairement » décomposer votre problématique en sous étapes logiques
2 – Réduire le volume de données
En développement
Limiter le nombre d’entités à lire dans le Reader ou utiliser un Sampler pour avoir un échantillon représentatif de vos données
Exporter des données échantillonnées au format .ffs en amont du développement
En production
Filtrer les types d’entités et données nécessaires (clause WHERE, Tester…)
Utiliser le SQL (SQLCreator, SQLExecutor, DatabaseJoiner)
Filtrer spatialement avec un rectangle englobant (BBOX) ou filtrer les données avec FeatureReader
Favoriser des formats rapides comme le CSV et bases de données spatiales indexées
En production
Filtrer les types d’entités et données nécessaires (clause WHERE, Tester…)
Utiliser le SQL (SQLCreator, SQLExecutor, DatabaseJoiner)
Filtrer spatialement avec un rectangle englobant (BBOX) ou filtrer les données avec FeatureReader
Favoriser des formats rapides comme le CSV et bases de données spatiales indexées
3 – Utiliser le cache à bon escient
Il est aussi contre-productif d’utiliser le cache lorsque l’on traite des données de type raster (images matricielles). En effet, la mise en cache de ces entités génère un énorme ralentissement du traitement. Il est possible de **créer des signets et de les réduire car cela aura pour effet de ne pas mettre en cache les Transformers dans ce dernier**.
4 – Réutiliser vos développements
Transformers personnalisés
5 – L’usage des paramètres
Les paramètres publiés permettent de rendre votre script plus adaptable et évolutif.
6 – **Lecture et écriture dynamique**
Le mode dynamique quant à lui permet de tout regrouper en un seul Reader et un seul Writer.
Grâce à une entité schéma, FME sera en mesure de reconstruire les sorties comme les entrées qui sont pourtant fusionnées.
Cela a aussi l’avantage de gérer le changement de structure des fichiers source de manière automatique tout en diminuant parfois fortement le temps de développement !
Astuce : l’outil Connexion des types d’entités permet les connexion en masse. Il est disponible dans Affichage > Fenêtres.
7 – Les fonctionnalités de répartitions
Que ce soit une répartition du type d’entités ou du jeu de données, ce paramétrage permet un grain énorme de productivité lorsque vous avez besoin d’exporter des données ayants un groupe similaire.
8 – Travailler la généricité des développements
9 – Se former et découvrir les Transformers
10 – Copier/coller et appliquer les paramétrages sur les types d’entités
Il existe une fonctionnalité pour appliquer des paramétrages sur l’ensemble des types d’entités.
copier/coller ou dupliquer la ligne sur les Transformers similaires ou de même « famille ». Tester/Testfilter, AttributeCreator/AttributeManager pour copier/coller les valeurs conditionnelles. Ces options, comme beaucoup sur FME sont disponibles via un clic droit.
copier/coller des Transformers eux-mêmes afin de récupérer des paramétrages similaires à mettre en œuvre.






[Extracting Geospatial Data from PDFs](https://fme.safe.com/blog/2018/08/convert-geospatial-pdf/)

[Data Validation and Quality Assurance with FME](https://cdn.safe.com/resources/technical-briefs/Data_Validation_and_Quality_Assurance_with_FME.pdf) (liste les différents types d'erreurs géométriques)

[4 methods for tracking data changes in FME](https://fme.safe.com/blog/2025/04/4-methods-for-tracking-data-changes-in-fme/)
1. Filtering by modification timestamps
2. Format-specific change tracking
3. Leverage Databricks’ Delta tables or other versioned storage systems to access historical versions and detect changes
4. Log-based change data capture (CDC) : Enable built-in CDC in systems like SQL Server to maintain a detailed log of all changes. FME can query these logs to build audit trails or rollback mechanisms.

Webinars :
a. [Managing Changing Data with FME: Part 1 – Compare & Detect](https://fme.safe.com/webinars/managing-changing-data-with-fme-part-1-compare-detect/)
b. [Managing Changing Data with FME: Part 2 – Flexible Approaches to Tracking Changes](https://fme.safe.com/webinars/managing-changing-data-with-fme-part-2-flexible-approaches-to-tracking-changes/)

[5 best practices for remote data processing in FME](https://fme.safe.com/blog/2025/04/5-best-practices-for-remote-data-processing-in-fme/)
1. **Process data where it lives** : Rather than pulling entire tables into FME to join or filter them, use SQL queries or the DatabaseJoiner transformer to perform operations directly at the source. This minimizes network traffic and takes advantage of your database’s built-in performance features like indexing.
2. **Apply filters at the source** : Use a WHERE clause in your Reader when working with attribute data, or go a step further with FeatureReader to combine attribute and spatial filtering.
3. **Cache files from the web when needed By enabling caching in the Reader or FeatureReader, you can avoid repeated downloads and enjoy faster runs.
4. **Take advantage of built-in connectors** : Connectors for popular cloud platforms and APIs like AWS S3, Azure Blob Storage, and ArcGIS Online. For less common APIs, you can still build custom integrations using HTTPCaller alongside Transformers like JSONFlattener or XMLFragmenter
5. **Choose the right format for cloud efficiency** Some modern formats are designed for partial access, so FME can retrieve only the data it needs without downloading the entire file. Consider using:
COG (Cloud Optimized GeoTIFF) for imagery, COPC for point clouds, ZARR for scientific or multidimensional arrays

eBook <a href="../documents/Spatial-Data-for-the-Enterprise-For-Dummies-Safe-Software-Special-Edition-FRENCH.pdf" target="_blank">les données spatiales dans l'entreprise</a>

Article blog INSER [FME et la résolution spatiale ESRI](https://www.inser.ch/fr/blog/fme-et-la-resolution-spatiale-esri) : 
*il est recommandé dans FME d’imposer ce snapping sur cette grille virtuelle afin de garantir que la donnée sortant de FME sera exactement celle qui sera enregistrée dans ArcGIS* -> **ArcSDEGridSnapper**

Article blog INSER [Systèmes de coordonnées suisses](https://www.inser.ch/fr/blog/systemes-de-coordonnees-suisses) :
*Pour simplifier l’utilisation de FME, l’utilisateur suisse peut partir du principe suivant :*
<ul><li>Données en MN03 -> EPSG:21781</li>
<li>Données en MN95 -> EPSG:2056</li></ul>

Article blog INSER [Transformation MN03 - MN95 et FME](https://www.inser.ch/fr/blog/transformation-mn03-mn95-et-fme)
<ul>
  <li>Reframe => **ReframeReprojector** : Mensuration officielle – Données SIG précises </li>
      
   <li>NTV2 – Grilles d’interpolation => **Reprojector** – **CsmapReprojector** : Données SIG de précision moyenne (quelques cm)</li>

<li>Transformation par bloc => **CoordinateExtractor** – **Offsetter** (ou **Affiner**)- **CoordinateSystemSetter** : image raster ou dans le cas où la géométrie des objets doit être conservée </li>
<li>Transformation par translation (shift) =>  **Offsetter** : données SIG de précision métrique</li>
</ul>






{% include note.html content="infos diverses sur FME" %}

