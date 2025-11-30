---
title: Shiny apps publiques
tags: [Shiny]
last_updated: December 2, 2023
keywords: shiny, apps
summary: "liste des applications shiny disponibles en ligne"
sidebar: mydoc_sidebar
permalink: Shiny_public.html
folder: mydoc
---

{% include note.html content="Ne jamais charger ou introduire des données personnelles dans les applications en ligne" %}



## Agricoles


##### Calcul UMOS

* Surfaces : <https://sca-vs-opdir.shinyapps.io/calc-umos-surfaces>

* TODO : surfaces+arbres+bétail

##### Contrôles 

* Rubriques Acontrol et schémas de réduction Annexe 8 : <https://sca-opdir.shinyapps.io/rubriques-acontrol>
* Ancienne version : <https://sca-opdir.shinyapps.io/controles-reductions-pdir> - pas à jour


##### Paiements directs

* Tableaux synoptiques : <https://sca-vs-opdir.shinyapps.io/tableaux-synoptiques-paiements-directs>

* BBS parser : <https://sca-opdir-vs.shinyapps.io/bbs-parser> (ancienne version : <https://sca-opdir.shinyapps.io/bbs-parser> - plus lente)

## Utilitaires

* Fusion de fichiers : <https://sca-opdir.shinyapps.io/fusion-de-fichiers>

* Agrégation de lignes : <https://sca-opdir.shinyapps.io/agregation-de-lignes>

## Autres infos

Déployer une app shiny sur github :

[https://hbctraining.github.io/Training-modules/RShiny/lessons/shinylive.html](https://hbctraining.github.io/Training-modules/RShiny/lessons/shinylive.html)

exporter l'app dans dossier docs
ensuite dans la console, se déplacer dans le dossier parent qui contient le docs
créer le dossier public sur github
git init
git add .
git commit -m "Ajout de l'app ShinyLive"
git remote add origin https://github.com/sca-opdir/info_BI.git
git branch -M main
git config --global http."https://github.com/".sslVerify false
git push -u origin main  
{% include links.html %}

