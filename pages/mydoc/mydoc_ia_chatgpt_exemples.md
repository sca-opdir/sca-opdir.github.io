---
title: ChatGPT - exemples d'utilisation
keywords: IA, IT, ChatGPT
last_updated: July 3, 2016
tags: [IA]
summary: "Exemples d'utilisation de ChatGPT"
sidebar: mydoc_sidebar
permalink: ChatGPT_exemples.html
folder: mydoc
---


## Correction des fautes de frappe après rédaction rapide

<div class="mycomment">NB : pour une raison inconnue, je n'ai pas réussi à faire respecter la numérotation (le 1er item est toujours corrigé à 1)</div>


<div class="chatgptIn"><br>
Dans le texte ci-dessous, corrige les fautes de frappe, sans apporter aucune autre modification et sans changer la numérotation :<br>
10. Gestion de proejts <br>
a. Planfiication de projet : défintiion objectifs, création échéancier, identification ressources, créattion plan, établissement des livrables<br>
b. Gestion des risques du projet : identification des risques, élaboration plan de contingence, gestion des problèmes, anlayse des risques, planfiication de la préposne aux risques<br>
c. Suivi et contrôle du projet : suvii avancement, analyse des écarts, gestion des modifications, évaluation qualité, contrôle des coûts<br>
</div><br><div class="chatgptOut"><br>
1. Gestion de projets<br>
a. Planification de projet : définition objectifs, création échéancier, identification ressources, création plan, établissement des livrables<br>
b. Gestion des risques du projet : identification des risques, élaboration plan de contingence, gestion des problèmes, analyse des risques, planification de la réponse aux risques<br>
c. Suivi et contrôle du projet : suivi avancement, analyse des écarts, gestion des modifications, évaluation qualité, contrôle des coûts<br>
</div>

## Extraire les tâches de chacun depuis des notes de réunion "en vrac"

<div class="chatgptIn"><br>
Le texte ci-dessus explique un processus de traitement de données ; pour chaque personne liste en utilisant des mots clés les tâches qu'il doit effectuer
Mylène prépare la base de données avec les manquements bordures tampon <br>
elle transmet le fichier à Marie qui regarde, pour chaque propriétaire et exploitant s'il y a lieu de faire une réduction ou pas (calcul de la réduction) ; si réduction, elle prépare les courriers pour les exploitants et les propriétaires ; les courriers propriétaires sont envoyés à Olivier qui se charge de l'envoi ; Fabrice se charge des courriers exploitants<br>
les courriers sont envoyés au même moment que le décompte paiements directs<br>
les réclamations propriétaires sont traitées par Olivier ; Fabrice s'occupe des réclamations des exploitants ; la décision d'accepter ou refuser la réclamation revient à Fabrice ; si la réclamation est acceptée, la réduction est annulée<br>
à la fin de la période de réclamation, Fabrice transmet à Mylène et Marie la liste des réductions acceptées pour l'import dans Acontrol ; Marie importe les résultats de la campagne dans Acontrol ; Mylène corrige la base de données
</div>
<br>
<div class="chatgptOut"><br>
Mylène:<br>
<ul>
<li>Préparer la base de données avec les manquements, bordures, et tampon. </li>
<li>Corriger la base de données à la fin de la période de réclamation.</li></ul><br>
Marie: <br>
<ul><li>Recevoir le fichier de Mylène. </li>
<li>Examiner, pour chaque propriétaire et exploitant, s'il est nécessaire de faire une réduction (calcul de la réduction). </li>
<li>Préparer les courriers pour les exploitants et les propriétaires en cas de réduction. </li>
<li>Importer les résultats de la campagne dans Acontrol. </li></ul><br>
Olivier: <br>
<ul><li>Recevoir les courriers propriétaires de Marie. </li>
<li>S'occuper de l'envoi des courriers propriétaires. </li>
<li>Traiter les réclamations propriétaires. </li>
<li>En cas de réclamation acceptée, annuler la réduction. </li></ul><br>
Fabrice: <br>
<ul><li>Recevoir les courriers exploitants de Marie. </li>
<li>S'occuper de l'envoi des courriers exploitants. </li>
<li>Traiter les réclamations des exploitants. </li>
<li>Décider d'accepter ou refuser la réclamation. </li>
<li>Transmettre à Mylène et Marie la liste des réductions acceptées pour l'import dans Acontrol. </li></ul>
</div>
<div class="mycomment">Pour obtenir la même chose sous forme de tableau à importer dans Excel</div>
<div class="chatgptIn"><br>
Présente les mêmes données sous forme de tableau (1 ligne par personne, 1ère colonne = nom de la personne, 2ème colonne = tâches à effectuer) ; sépare les colonnes par une barre verticale (ne formate pas le tableau, laisse-le sous forme de texte à copier) 
</div><br>
<div class="mycomment">Pour obtenir une liste des tâches de façon chronologique</div>
<div class="chatgptIn"><br>
Pour ces mêmes données, résume de façon concise sous forme de liste les tâches à effectuer en utilisant des mots-clés en maintenant leur ordre chronologique tel qu'indiqué dans le texte en entrée et indique entre parenthèses la personne responsable de la tâche
</div><br>
<div class="chatgptOut"><br>
1. Préparer la base de données avec manquements, bordures, tampon (Mylène).<br>
2. Transmettre le fichier à Marie (Mylène). <br>
3. Examiner et calculer les réductions pour chaque propriétaire et exploitant (Marie). <br>
4. Préparer les courriers pour exploitants et propriétaires en cas de réduction (Marie). <br>
5. Envoyer les courriers propriétaires à Olivier (Marie). <br>
6. Envoyer les courriers exploitants à Fabrice (Marie). <br>
7. Envoyer les courriers au même moment que le décompte paiements directs. <br>
8. Traiter les réclamations propriétaires (Olivier). <br>
9. Traiter les réclamations des exploitants (Fabrice). <br>
10. Décider d'accepter ou refuser la réclamation (Fabrice). <br>
11. Annuler la réduction si la réclamation est acceptée (Fabrice). <br>
12. À la fin de la période de réclamation, transmettre la liste des réductions acceptées à Mylène et Marie (Fabrice). <br>
13. Importer les résultats de la campagne dans Acontrol (Marie). <br>
14. Corriger la base de données (Mylène). <br>
</div>

<br>
## Extraire des éléments d'un XML

<div class="chatgptIn"><br>
Extrais le nom des éléments et enlève le namespace "n0" dans le code XML ci-dessous : <br>
<n0:E_KLZonenbeitrag>true</n0:E_KLZonenbeitrag><br>
<n0:E_KLAllgHangbeitrag>true</n0:E_KLAllgHangbeitrag><br>
<n0:E_KLSteillagenbeitrag>true</n0:E_KLSteillagenbeitrag><br>
<n0:E_KLRebHangbeitrag>false</n0:E_KLRebHangbeitrag><br>
<n0:E_KLAlpungsbeitrag>true</n0:E_KLAlpungsbeitrag><br>
<n0:E_KLSoemmerungsbeitrag>false</n0:E_KLSoemmerungsbeitrag><br>
<n0:E_VSBasisbeitrag>true</n0:E_VSBasisbeitrag><br>
<n0:E_VSZonenbeitrag>true</n0:E_VSZonenbeitrag><br>
<n0:E_VSOffeneAckerflaecheundDauerkulturen>true</n0:E_VSOffeneAckerflaecheundDauerkulturen><br>
<n0:E_VSEinzelkultur>true</n0:E_VSEinzelkultur><br>
<n0:E_BDQualitaetsbeitrag>true</n0:E_BDQualitaetsbeitrag><br>
<n0:E_BDQualitaetsbeitragSoem>false</n0:E_BDQualitaetsbeitragSoem><br>
<n0:E_BDVernetzungsbeitrag>true</n0:E_BDVernetzungsbeitrag><br>
<n0:E_LQBeitrag>true</n0:E_LQBeitrag><br>
<n0:E_LQBeitragSoem>false</n0:E_LQBeitragSoem><br>
<n0:E_PSBiolandbau>false</n0:E_PSBiolandbau><br>
    
</div><br>

<div class="chatgptOut"><br>

Voici les noms des éléments sans le namespace "n0" : <br>
````
E_KLZonenbeitrag
E_KLAllgHangbeitrag
E_KLSteillagenbeitrag
E_KLRebHangbeitrag
E_KLAlpungsbeitrag
E_KLSoemmerungsbeitrag
E_VSBasisbeitrag
E_VSZonenbeitrag
E_VSOffeneAckerflaecheundDauerkulturen
E_VSEinzelkultur
E_BDQualitaetsbeitrag
E_BDQualitaetsbeitragSoem
E_BDVernetzungsbeitrag
E_LQBeitrag
E_LQBeitragSoem
E_PSBiolandbau
```
</div>



## Rédaction newsletter à partir d'idée en vrac sur le même style qu'un modèle

<div class="chatgptIn"><br>
Je suis employée dans l'administration publique et j'aimerais un court texte à placer dans une newsletter à l'intention de personnes actives en agriculture pour informer des éléments suivants : l'office des paiements directs et l'office vétérinaire vont organiser une campagne de contrôles des sorties hivernales du bétail cet hiver - les sorties seront contrôlées par des films vidéos de cinq sorties hivernales au cours de l'hiver -  une dizaines d'exploitations à travers tout le canton seront sélectionnés et subiront ces contrôles - ces contrôles sont un bon moyen d'améliorer la confiance avec le monde non agricole. <br>
L'expression " vidéos de cinq sorties hivernales" doit figurer tel quel. Ce texte informatif ne s'adresse pas directement aux personnes concernées par ces contrôles, mais veut informer le reste de la population que ces contrôles auront lieu. Le texte doit être court, chaleureux et ne pas utiliser l'impératif, long de 50 mots maximum et tenir dans 1 paragraphe. <br>
Le texte doit être fluide et engageant, écrit dans un style similaire à ce paragraphe : " L’Ecole d’agriculture du Valais (EAV) célèbre ses 100 ans en 2023. Pour clore ce jubilé, le Service de l’agriculture a mandaté l’historienne Delphine Debons afin de concevoir un ouvrage original, sous la forme d’un coffret réunissant un livre d’histoire et cinq cahiers en lien avec des thématiques incontournables pour l’avenir de l’agriculture valaisanne. Ce coffret est publié par les Archives de l’Etat du Valais, dans la série des Cahiers de Vallesia."
</div>
<br>
<div class="chatgptOut">
<br>Cet hiver, l'Office des paiements directs et l'Office vétérinaire lancent une campagne de contrôles des sorties hivernales du bétail. Des films vidéos de cinq sorties seront capturés dans une dizaine d'exploitations à travers le canton. Cette initiative renforce la transparence de l'agriculture, favorisant ainsi la confiance avec le monde non agricole.
</div>
<br>


## Correction des majuscules, de la ponctuation et des exposants dans un texte
<div class="chatgptIn">
<br>
Ré-écris le texte ci-dessous en corrigeant uniquement ces 3 choses : 
1. rajoute les "." et les "," qui manquent <br>
2. met en majuscule les lettres des mots qui devraient commencer par une majuscule (c'est-à-dire ceux en début de paragraphe ou après un ".")<br>
3. met en exposant ce qui devrait l'être (par exemple dans 1er "er" devrait être placé comme exposant)
<br>
Mylène prépare la base de données avec les manquements bordures tampon<br>
en 1er elle transmet le fichier à Marie qui regarde, pour chaque propriétaire et exploitant s'il y a lieu de faire une réduction ou pas (calcul de la réduction) ; si réduction, elle prépare les courriers pour les exploitants et les propriétaires ; les courriers propriétaires sont envoyés à Olivier qui se charge de l'envoi ; Fabrice se charge des courriers exploitants<br>
les courriers sont envoyés au même moment que le décompte paiements directs<br>
les réclamations propriétaires sont traitées par Olivier ; Fabrice s'occupe des réclamations des exploitants. la décision d'accepter ou refuser la réclamation revient à Fabrice. si la réclamation est acceptée, la réduction est annulée<br>
à la fin de la période de réclamation, Fabrice transmet à Mylène et Marie la liste des réductions acceptées pour l'import dans Acontrol. la 1ère importe les résultats de la campagne dans Acontrol ; la 2ème corrige la base de données<br>
</div>
<br>
<div class="chatgptOut"><br>
Mylène prépare la base de données avec les manquements, bordures et tampon. En 1ᵉʳ, elle transmet le fichier à Marie qui regarde, pour chaque propriétaire et exploitant, s'il y a lieu de faire une réduction ou pas (calcul de la réduction) ; si réduction, elle prépare les courriers pour les exploitants et les propriétaires. Les courriers propriétaires sont envoyés à Olivier qui se charge de l'envoi ; Fabrice se charge des courriers exploitants. Les courriers sont envoyés au même moment que le décompte paiements directs. Les réclamations propriétaires sont traitées par Olivier ; Fabrice s'occupe des réclamations des exploitants. La décision d'accepter ou refuser la réclamation revient à Fabrice. Si la réclamation est acceptée, la réduction est annulée.
À la fin de la période de réclamation, Fabrice transmet à Mylène et Marie la liste des réductions acceptées pour l'import dans Acontrol. La 1ᵉʳᵉ importe les résultats de la campagne dans Acontrol ; la 2ᵉᵐᵉ corrige la base de données.
</div>
<br>



<!--
<div id="mycontainer">
    <div id="mylabel">I'm a Box</div>
</div>
-->







{% include links.html %}
