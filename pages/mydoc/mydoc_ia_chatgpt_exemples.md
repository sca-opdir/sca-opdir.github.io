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









<!--
<div id="mycontainer">
    <div id="mylabel">I'm a Box</div>
</div>
-->







{% include links.html %}
