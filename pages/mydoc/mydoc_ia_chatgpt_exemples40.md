---
title: ChatGPT 4.0 - exemples d'utilisation (y.c. plugins)
keywords: IA, IT, ChatGPT
last_updated: December 4, 2023
tags: [IA]
summary: "Exemples d'utilisation de ChatGPT (4.0)"
sidebar: mydoc_sidebar
permalink: ChatGPT_exemples40.html
folder: mydoc
---


## Repérer des termes dupliqués dans une liste 

<div class="mycomment">
NB : ne fonctionnait pas avec GPT-3.5
</div>

<div class="chatgptIn" markdown=1>
***Y a-t-il des verbes qui reviennent plus d'une fois dans la liste ci-dessous ? Si oui, lesquels ?*** <br>
propose / réalise / estime / crée / aides à [formuler/créer/préparer/élaborer/me préparer pour ...] pour [une start-up qui ...] / identifie / évalue [la performance] / élabore / rédige / donne / formule / mène / génère / développe /écris / cartographie [le parcours ...] / énumère / prépare / utilise [l'analyse SWOT] pour concevoir / examine [notre proposition/ce site web] et suggère [des façons de l'améliorer pour la rendre plus ...] / conçois / fournis / analyse [le parcours/une crise récente ...] / examine [le CV pour ...] et évalue / élabore / estime / présente / suggère / effectue / guide [le client à travers le processus] / conçois / imagine 
</div>

<div class="chatgptOut">
  <br>
Oui, il y a des verbes qui reviennent plus d'une fois dans la liste. Voici les verbes qui apparaissent plus d'une fois :<br>
"propose" apparaît deux fois.<br>
"réalise" apparaît deux fois.<br>
"estime" apparaît trois fois.<br>
"crée" apparaît deux fois.<br>
</div>

<hr>


## Compter l'occurrence des mots 

<div class="mycomment">
NB : ne fonctionnait pas avec GPT-3.5 ; prompt à affiner (mots <i>contribution</i> et <i>contributions</i> sont encore comptés séparément)
</div>

<div class="chatgptIn" markdown=1>
***Compte le nombre d’occurrence totale de chaque mot dans le texte ci-dessous ; réponds par un tableau contenant le mot en 1ère colonne et l’occurrence en 2ème colonne; le tableau doit donner le résultat pour tout le texte (1 ligne par mot, il ne doit pas y avoir de doublons dans la 1ère colonne) ; le tableau doit être trié par ordre décroissant du nombre d’occurrences ; ne prends en compte que les mots de plus de 3 lettres ; un mot et ses formes dérivées ne doivent être comptabilisés qu’une fois.*** Par exemple pour la phrase “tu es agriculteur et je suis agricultrice” le résultat doit être :
être;2<br>
agriculteur;2<br>

Le texte à analyser est : <br>
Contributions au paysage cultivé pour le maintien d’un paysage rural ouvert : outre la contribution pour surfaces en pente et la contribution d’estivage, une contribution pour les exploitations qui ont une part élevée de surfaces en forte pente est également allouée sous cette rubrique. De plus, les exploitations qui estivent leurs animaux reçoivent une contribution de mise à l’alpage. 
Contributions à la sécurité de l’approvisionnement pour le maintien d’un approvisionnement sûr de la population en denrées alimentaires : Elles sont versées en fonction de la surface, à condition que les exploitations respectent une charge minimale en bétail sur les surfaces herbagères. La contribution pour les terres ouvertes et les cultures pérennes contribue en outre à encourager les grandes cultures et notamment la culture de céréales fourragères en Suisse.

</div>

<div class="chatgptOut" markdown=1>
  <br>
Voici un tableau qui répertorie le nombre d'occurrences de chaque mot (de plus de 3 lettres) dans le texte fourni, trié par ordre décroissant d'occurrences :<br>

<table border="1">
  <tr>
    <th>Mot</th>
    <th>Occurrence</th>
  </tr>
  <tr>
    <td>pour</td>
    <td>5</td>
  </tr>
  <tr>
    <td>contribution</td>
    <td>5</td>
  </tr>
  <tr>
    <td>surfaces</td>
    <td>3</td>
  </tr>
  <tr>
    <td>exploitations</td>
    <td>3</td>
  </tr>
  <tr>
    <td>contributions</td>
    <td>2</td>
  </tr>
  <tr>
    <td>paysage</td>
    <td>2</td>
  </tr>
  <tr>
    <td>maintien</td>
    <td>2</td>
  </tr>
  <tr>
    <td>outre</td>
    <td>2</td>
  </tr>
  <tr>
    <td>pente</td>
    <td>2</td>
  </tr>
</table>


<br>
Notez que seules les 10 premières lignes sont affichées ici pour des raisons de concision. Si vous avez besoin de la liste complète, faites-le moi savoir. ​​
</div>

## Accéder à un PDF stocké à une URL et générer un document (.docx ou .pdf) du texte traduit en allemand (plugin *AskYourPDF*)

<div class="mycomment" markdown=1>NB : sans préciser d'utiliser le plugin *AskYourPDF*, cela n'a pas marché car il utilise *WebPilot* et n'arrive pas à lire le pdf.
</div>
  
<div class="chatgptIn">
  <br>
Accède au contenu de la page https://www.vs.ch/documents/15726774/18619542/Mod%C3%A8le_procuration+saisie+internet+donn%C3%A9es+agricoles_FR.pdf/32a79212-2c21-03a6-34f3-15e8816e7917?t=1678542930897 en utilisant le plugin AskYourPDF, puis génère un document docx contenant la traduction en allemand de ce contenu.
</div>

ChatGPT retourne un lien qui permet de télécharger le document traduit en .docx ou .pdf.

## Connaissance sur le monde réel avec le plugin *Wolfram*

<div class="chatgptIn">
  <br>
Réponds à cette question en utilisant le plugin Wolfram ; est-ce que tu connais la plante Bunias orientalis ? est-ce que tu peux en faire une illustration ?
</div>d



## Créer des GPTs personnalisés

https://openai.com/blog/introducing-gpts 

https://www.whatplugin.ai/ (plugins et GPTs)

concevant des modèles plus spécialisés pour des domaines et des tâches plus spécifiques
démarrer une conversation avec le GPT Builder en lui expliquant ce que vous attendez de lui.

Donnez-lui un nom et une description pour votre futur GPT, puis des instructions. Sélectionnez ensuite les fonctionnalités ChatGPT que vous souhaitez que votre GPT personnalisé possède. Par exemple, la navigation sur le web, la génération d’images par le biais de DALL-E ou des compétences en matière de codage.

Vous pouvez même intégrer des données du monde réel pour connecter votre GPT à une base de données externe, à une boîte de réception ou à un site d’e-commerce.
https://www.zdnet.fr/guide-achat/avec-chatgpt-creez-vos-propres-gpt-personnalises-39962626.htm

## . Interpréter le contexte d’une image
nalyser les images et vous en faire une description précise. Il est aussi capable de vous suggérer de nouvelles idées à partir de l’image.

https://www.blogdumoderateur.com/comment-utiliser-gpt-4-exemples/

## Générer des textes redoublant de créativité
La créativité est à l’honneur avec le nouveau ChatGPT propulsé par GPT-4. Il répond beaucoup mieux aux attentes créatives des utilisateurs. Ainsi, ce nouveau modèle d’IA peut apprendre à reproduire le style d’écriture d’un utilisateur afin de générer des idées qui correspondent mieux aux prompts demandés. GPT-4 peut rendre des résultats bluffants pour des compositions de chansons ou des écritures de scénarios par exemple.

Le cas ci-dessous est un exemple dévoilé par OpenAI, GPT-4 est capable de répondre à ce prompt : « Expliquez l’intrigue de Cendrillon dans une phrase où chaque mot doit commencer par la lettre suivante de l’alphabet de A à Z, sans répéter aucune lettre. »

https://www.blogdumoderateur.com/comment-utiliser-gpt-4-exemples/

## Résumer des textes de 25 000 mots
Autre point fort : GPT-4 peut gérer plus de 25 000 mots, contre environ 3000 mots pour son prédécesseur. Cela signifie qu’il peut résumer des documents plus longs mais aussi créer des contenus plus longs à partir d’un prompt. À la clé : des conversations prolongées avec le nouveau ChatGPT !

## 4. Transformer des croquis en sites web ou applications
À partir d’un simple dessin sur papier, le modèle d’IA va être capable de générer un site web fonctionnel.

## Créer un jeu vidéo en 1 minute seulement
GPT-4 peut aussi vous générer du code très rapidement pour vous aider à concevoir des jeux vidéo. L’exemple ci-dessous est frappant : l’utilisateur a pu recréer le célèbre jeu de Pong en 60 secondes grâce au nouveau modèle d’IA.

## Recréer le jeu Snake sans compétences en JavaScript
Toujours côté gaming, un utilisateur a réussi à recréer « le jeu Snake qui fonctionne dans votre navigateur en utilisant Chat GPT-4 et Replit avec ZÉRO connaissance de Javascript, le tout en moins de 20 minutes. »  De quoi donner envie de tester le nouveau modèle d’IA !

## Créer une extension Chrome
Dans l’exemple ci-dessous, l’utilisateur a testé un prompt avec des consignes pour créer une extension Chrome. Il a réussi à créer son extension, sans aucune expérience de codage. GPT-4 a généré du code pour lui et l’a accompagné étape par étape pour réaliser ce projet. Impressionnant ! En revanche, cela pourrait bien faciliter la tâche aux cybercriminels qui développent des fausses extensions au nom de ChatGPT…

8. Apprendre une langue rapidement
Lors de la présentation de GPT-4, OpenAI a présenté des exemples d’entreprises qui utilisent déjà son nouveau modèle d’AI. Parmi elles : Duolingo, une application reconnue pour l’apprentissage de langues étrangères. GPT-4 est multilingue à un stade avancé, ce qui a permis à Duolingo de lancer des nouveautés, dont une qui se nomme Role Play, permettant de discuter avec un personnage fictif pour progresser dans une autre langue.

. Traiter des questions juridiques complexes
GPT-4 peut aussi enfiler la robe d’avocat pour répondre à des questions juridiques. Un exemple ci-dessous est donné par le CEO de DoNotPay : un chatbot de services juridiques. Il indique que son entreprise « travaille à l’utilisation du GPT-4 pour générer des « procès en un clic » permettant de poursuivre les robocallers pour 1 500 dollars. »


## Reconnaissance d'image

## Génération d'images

## Manuel d'utilisation à partir d'image


## Demander la critique d'une page web

## Analyser un lien web


