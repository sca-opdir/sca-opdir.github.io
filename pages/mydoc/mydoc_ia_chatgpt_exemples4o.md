---
title: ChatGPT 4o - exemples d'utilisation
keywords: IA, IT, ChatGPT
last_updated: July 13, 2025
tags: [IA]
summary: "Exemples d'utilisation de ChatGPT (4o)"
sidebar: mydoc_sidebar
permalink: ChatGPT_exemples4o.html
folder: mydoc
---



* Mémoire de 100'000 mots (128k tokens) (ChatGPT 3.5 : 6'000)
* 60% de moins d’hallucinations que GPT-3.5 d'après L’Alignement Research Center, 
* Vision intégré, capacités de d’analyser des fichiers excel et de coder en Python, plugins, custom GPTs, connecté à internet

* Utilisation de la commande vocale

* Permet de soumettre des prompts "augmentées" : ajout d'images, fichiers excel à analyser, fichiers pdf/word/etc., connexion à internet

([source](https://acoustic-licorice-c24.notion.site/1-Qu-est-ce-que-GPT-4o-4e4d1ef2b51645d0ac9c5e15cbcd5cb1))

## Exemples de prompt

_créer un arbre de décision_

crée un arbre de décision pour la procédure décrite ci-dessous [décrire la procédure, par exemple de demande d'inscription tardive]
[...]
génère un code Mermaid pour cet arbre de décision
[...]

-> copier/coller le code Mermaid dans un outil de dessin de diagramme, par exemple Excalidraw


_prompt de veille informationnelle_ par Jean-Baptiste Berthoux : [lien](../documents/prompt pour la veille informationnelle JBB.pdf])


cours _Améliorer l’utilisation de l’IA_, Etat du Valais, par Nicolas Oggier : [lien interne](\\infra.vs.ch\dfs\SCA-DLW\PDIRECTS\1_Marie\6_autres infos\formations continues\Améliorer l’utilisation de l’IA  2025 V2 - Etat du Valais.pdf)


tâche > contexte > exemple > rôle > format > ton

```
Tu es un expert en formation dans le domaine de l'IA. 
Tu disposes des compétences suivantes:
Tu es spécialisé dans la création de prompts. 
Tu maitrises parfaitement la création de scripts pour faire des courts métrages vidéo sur des sujets techniques relatifs à l'IA.
Je souhaite que tu réalises un synopsis pour la création d'une vidéo qui explique comment élaborer un prompt parfait en 2025 pour une IA comme ChatGPT, par exemple.
Ce script doit contenir des informations pertinentes  liées au sujet.
Il doit permettre d'élaborer une vidéo de 2 min au maximum
Il doit être en français
Assure-toi de ne fournir que des informations fiables.
Cette vidéo sera utilisée pour introduire la réalisation de prompts parfaits.
```

la structure du prompt en 2025

ROLE
Tu es un expert en \[DÉCRIRE THÉMATIQUE(S) CLÉS\]. 
Tu disposes des compétences suivantes \[DÉCRIRE\]. 
TACHE
Je souhaite \[DÉCRIRE VOTRE TACHE/OBJECTIF\].
FORMAT DE REPONSE ATTENDU
\[CARACTERISTIQUE 1\]
\[CARACTERISTIQUE 2\]
Etc...
POINTS DE VIGILANCE
Assure-toi de justifier ta réponse en te basant sur des sources fiables. Ta réponse ne doit pas:
\[ANTI- CARACTERISTIQUE 1\]
\[ANTI- CARACTERISTIQUE 2\]
Etc...
CONTEXTE
Pour le contexte : \[DECRIRE AVEC LE PLUS DE DETAILS POSSIBLES VOTRE CONTEXTE\]

Optimiser les prompts
- début : structuration claire, rôle précis
- centre : donner les caractéristiques attendues, contexte et objectif, critères spécifiques
- fin : techniques complémentaires

Exemple de Prompt
###Mission : ...
Rôle : ...
Caractéristiques : texte court, percutant, appel à l’action clair
Contexte : ...
Objectif : ...
###
###Règles :
- Maximum xxx mots par phrase.
- Style xxxx
###
###Exemple de xxx réussi :
...
###

## Exemples d'utilisation

* **demander l'analyse d'un fichier excel** (ChatGPT utilise alors du code Python) : "Suppose que tu es un analyste de données et que tu dois analyser les résultats d'une enquête de satisfaction client.
Analyse les réponses du fichier 'satisfaction_client_banque_suisse.xlsx' pour identifier les tendances et les points critiques. Propose des visualisations adéquates.
Ensuite, crée un rapport détaillé incluant des graphiques, des conclusions basées sur les données et des recommandations pour améliorer la satisfaction client."
* **répondre à un email passé en capture d'écran** : "Suppose que tu es un assistant personnel et que ton objectif est d'améliorer la qualité des emails professionnels envoyés par ton employeur. Analyse la capture d'écran d'un email reçu. Ensuite, rédige une réponse à cet email."
* **synthèse d'un fichier PDF chargé en pièce jointe** : "Suppose que tu es un analyste de données chargé de synthétiser un rapport de recherche de 120 pages en un résumé exécutif.
D'abord, analyse le rapport de recherche fourni dans le fichier PDF 'rapport IA'. Identifie les points clés, les statistiques importantes et les conclusions principales.
 Rédige ensuite un résumé clair et concis entre entre 1000 et 1500 mots, en veillant à inclure toutes les informations essentielles de manière structurée et accessible."
* **utiliser la connexion Internet** : "Suppose que tu es un journaliste d'investigation et que tu dois extraire les informations essentielles d'une série d'interviews sur la démission le 12 janvier 1989 d’Elisabeth Kopp.
  Commence par faire des recherches en ligne pour trouver les interviews pertinentes. Utilise les ressources trouvées pour identifier les points clés, les citations importantes et les faits saillants.
Ensuite, organise ces informations de manière structurée et propose une structure pour ton article, incluant un titre accrocheur, une introduction, le corps de l'article et une conclusion".

([source](https://file.notion.so/f/f/e0c4cd4c-5dcc-4d82-b312-433753e87d14/4ab9ad2d-2bdb-4904-ba8c-b9e43924ca52/Inter_-_17_Juin_vf.pdf?id=ea0ab4a0-2f4b-4e8d-bbde-2733fb1275c6&table=block&spaceId=e0c4cd4c-5dcc-4d82-b312-433753e87d14&expirationTimestamp=1718949600000&signature=_a3ZrDAE8lNMhhii9fF04jyETrRPj7W2iyWz-PPJPfM&downloadName=Inter+-+17+Juin_vf.pdf))


## Exemples de types de tâches

### "Classiques"

**#1 - Générer des idées**

Je suis un [profession]. J'ai besoin de générer des idées pour [un projet spécifique]. Pouvez-vous me proposer des idées créatives et innovantes en lien avec ce domaine ?

**#2 - Corriger et écrire**

Je dois rédiger/corriger [type de document]. Voici les détails : [détails du document]. Pouvez-vous m'aider à écrire/corriger ce texte en gardant un ton [professionnel/amical/formel]

**#3 - Vulgariser un concept**

Je dois expliquer [concept complexe] à [public cible]. Pouvez-vous simplifier ce concept pour le rendre compréhensible par [public cible] ?

**#4 - Traduire des textes**

J'ai besoin de traduire le texte suivant de [langue source] à [langue cible] : [texte]. Pouvez-vous m'aider à le traduire de manière précise tout en conservant le ton et le style du texte original ?

**#5 - Aide au code / excel**

Je travaille sur un projet de [langage de programmation] et j'ai besoin d'aide pour [description du problème ou de la tâche]. Voici le code actuel :  [code]. Pouvez-vous m'aider à résoudre ce problème/améliorer ce code ?

**#6 - Aide à la réflexion**

Je suis en train de réfléchir à [sujet spécifique] et j'ai besoin d'aide pour structurer mes idées et développer une réflexion approfondie. Pouvez-vous me guider dans cette réflexion en me posant des questions pertinentes et en proposant des angles d'approche ?


### "Augmentées"

**#7 - Analyse d'un fichier texte**

J'ai un fichier texte qui contient une liste de tâches pour mon équipe. Pouvez-vous me proposer un moyen d'organiser ces tâches de manière efficace et rationnelle ?

**#8 - Analyse d'une image**

J'ai une image d'un organigramme que j'aimerais comprendre. Pouvez-vous analyser cette image et m'expliquer l’organisation de l’entreprise?

**#9 - Recherche sur internet**

Je travaille sur un projet lié à l'industrie des énergies renouvelables. Pouvez-vous effectuer une recherche sur internet pour trouver les dernières tendances et innovations dans ce domaine ?

**#10 - Analyse d'un fichier Excel**

J'ai un fichier Excel qui contient les données de vente de mon entreprise pour le dernier trimestre. Pouvez-vous analyser ces données et me donner un aperçu de nos performances de vente ?

([source](https://acoustic-licorice-c24.notion.site/1-Qu-est-ce-que-GPT-4o-4e4d1ef2b51645d0ac9c5e15cbcd5cb1))

{% include links.html %}
