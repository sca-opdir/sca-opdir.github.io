---
title: SAP webi
keywords: BI
last_updated: June 18, 2024
tags: [BI]
summary: "diverses infos sur SAP webi"
sidebar: mydoc_sidebar
permalink: SAPwebi_autres_infos.html
folder: mydoc
---

### Concaténation de chaines

Par ex: pour agréger en concaténant City par State

[source](https://community.sap.com/t5/technology-blogs-by-members/string-aggregation-on-webi-report-level/ba-p/13168326)

To achieve the result follow the steps:

1) First drag State & City objects on report and sort result by State and City in ascending order.

2) Create dimension like

Cities =[City]+";"+Previous(Self;([State]))

3)Create measure like

length_cities=Length([Cities])

4) Create another measure to calculate rank

Ranking =Rank([length_cities];[City];([State]))

5) Apply report level filter using newly created measure Ranking

where Ranking = 1

6) Create another dimension

Final_Cities  =NoFilter([Cities])

7) Drag this Final_Cities to report & then hide the column City.

### (suite) Pour afficher 1 ligne par valeur concaténée + valeur concaténée
à l'étape précédente, c'est seulement le rank 1 qui contient toutes les valeurs concaténées, il faut donc remplacer par la valeur qui les contient toutes au niveau d'agrégation souhaitée ; la variable que l'on veut donc afficher c'est celle qui a le plus de caractères
1) Créer une variable pour calculer la longueur de chaque chaîne de caractères :
=Length([concatNoParc])
Cette variable calcule la longueur de chaque chaîne de caractères dans [concatNoParc].
2) Créer une variable pour identifier la chaîne de caractères la plus longue :
=If([LengthVar] = Max([LengthVar]) In ([clé_parcelle])) Then [concatNoParc]
Cette variable compare la longueur de chaque chaîne de caractères avec la longueur maximale dans le contexte de [clé_parcelle] et retourne la chaîne de caractères correspondante si elle est la plus longue.
3) Créer une mesure pour afficher la chaîne de caractères la plus longue :
=Max([LongestStringVar]) In ([clé_parcelle])



### Join et identifier les valeurs manquantes d'un côté et de l'autre

fusionner les dimensions, créer une nouvelle mesure -> attention à bien mettre comme détail de la dimension fusionnée

[source](https://japprendslabi.fr/sap/sap-bi-web-intelligence-fiori/croiser-les-dimensions-issues-de-requetes-differentes-dans-un-meme-tableau/)
