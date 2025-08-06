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

[Traiter les données distantes avec FME](https://www.veremes.com/actus/traiter-les-donnees-distantes-avec-fme)

Les Transformers de jointure disponibles dans FME (FeatureMerger et FeatureJoiner) nécessitent de lire l’ensemble des données dans FME au préalable.

Si la table de référence contient de nombreux enregistrements, sa lecture complète est pénalisante et il sera préférable de recourir à un **DatabaseJoiner**.

Si les tables appartiennent à la même base de données, vous pouvez directement **réaliser la jointure dans la base de données** et exploiter son résultat dans FME. Cela sera encore plus efficace puisque la base de données pourra s’appuyer pleinement sur ses indexes pour comparer les enregistrements.

Qu’est-ce qu’un **index** ? Pour une base de données, un index est un mécanisme accélérateur de recherche, de façon similaire à la table des matières d’un document qui permet d’accéder plus rapidement à une section spécifique.

SQL permet de réaliser des opérations bien plus élaborées qu’une simple jointure, autorisant la mise en œuvre d’algorithmes complexes basés sur le parcours de graphe, la récursivité ou toute librairie de fonctions disponibles sur votre base de données (par exemple PostGIS ou pgRouting pour PostgreSQL).

Lorsque les données lues en base doivent être filtrées pour n’en conserver qu’un sous-ensemble, lire la totalité de la table dans FME avant de sélectionner ce sous-ensemble (par exemple avec un Tester) n’est pas très efficace. Remplacer par un Reader  exploitant le paramètre « Clause Where »

Si les enregistrements à lire doivent correspondre à une restriction géographique (emprise d’intérêt, limite administrative, …), plutôt que lire la totalité des données puis employer un SpatialFilter, il est préférable d’utiliser un **FeatureReader**, qui permet de combiner **filtrage spatial et attributaire**.

Fichiers directement accessibles par une URL : FME permet depuis de nombreuses années de lire directement des jeux de données en spécifiant une URL ; limiter le nombre de téléchargements en activant dans le FeatureReader un « cache » spécifique dont la durée de validité peut être réglée à votre convenance.

Données accessibles via un service normalisé : FME permet également d’exploiter des services d’accès aux données tels que WFS par exemple. Il est alors primordial de paramétrer le Reader ou FeatureReader avec un filtre pour limiter la recherche selon des propriétés d’attribut.
suivant les formats, le filtre spatial proposé par l’interface du FeatureReader peut s’appliquer avant ou après récupération des données du service, ce qui peut impacter fortement le résultat lorsque le service limite le nombre d’objets retournés. 

Données accessibles via une API : Dans le cas où l’API est suffisamment populaire, il est fréquent que FME dispose déjà d’un Transformer qui gère tous les aspects du dialogue avec le serveur. L’utilisateur FME n’a alors pas à s’occuper des « détails techniques » et peut directement employer le « Connector » adapté au service. 
Pour une API moins populaire, l’utilisateur FME doit gérer lui-même le dialogue avec un enchaînement de Transformers HTTPCaller entrecoupés de JSONFragmenter / JSONFlattener ou de XMLFragmenter / XMLFlattener suivant le langage de communication proposé par le service. 

dans le Cloud : Lorsque les données sont stockées dans le cloud, que ce soit sous forme de fichiers ou de bases de données, il est recommandé de les exploiter avec une instance FME située dans le même datacenter pour améliorer les performances mais aussi pour diminuer la consommation d’énergie correspondant au transport des données.

L’accès en lecture ou écriture à des systèmes de stockage par objet tels que AWS S3 ou Azure Blob Storage constitue un cas particulier. Il est nécessaire d’utiliser S3Connector ou AzureBlobStorageConnector pour réaliser les opérations de listage, lecture et écriture et échanger des fichiers avec son disque local. 

depuis quelques années, des formats de nouvelle génération tirent parti de la capacité offerte par le protocole HTTP d’accéder à une partie seulement d’un fichier distant sans imposer son téléchargement complet.

le format Cloud-Optimized-Geotiff ou COG permet d’exploiter une portion d’une image distante tout en minimisant les transferts réseaux

les formats Cloud-Optimized-Point-Cloud ou COPC pour le stockage des nuages de points (souvent issus de capteurs LIDAR), ZARR pour le stockage de tableau de résultats multidimensionnels et Seek-Optimized-Zip ou SOZip pour stocker des fichiers de tout type

[10 conseils pour gagner en productivité avec FME](https://www.veremes.com/actus/10-conseils-pour-gagner-en-productivite-avec-fme)
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



{% include links.html %}




{% include note.html content="infos diverses sur FME" %}

