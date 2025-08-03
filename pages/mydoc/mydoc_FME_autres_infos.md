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

eBook <a href="../documents/Spatial-Data-for-the-Enterprise-For-Dummies-Safe-Software-Special-Edition-FRENCH.pdf" target="_blank">les données spatiales pour l'entreprise</a>

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

