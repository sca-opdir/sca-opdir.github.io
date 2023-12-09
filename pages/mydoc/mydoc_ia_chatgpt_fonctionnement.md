---
title: Fonctionnement de ChatGPT
keywords: IA, IT, ChatGPT
last_updated: December 09, 2023
tags: [IA, ChatGPT]
sidebar: mydoc_sidebar
permalink: ChatGPT_fonctionnement.html
folder: mydoc
---

*Sources:*
* Test


# Accès

* Via la [plateforme web](https://chat.openai.com/)
* Via l'API
* Via le cloud (ex. : Microsoft offre également la version payante de ChatGPT via sa plateforme Azure, ce qui permet aux entreprises de l'intégrer facilement dans leurs applications et services.)

# Sous le capot de ChatGPT

Des briques pour comprendre (un peu) le fonctionnement de ChatGPT

## NLP

https://datascientest.com/introduction-au-nlp-natural-language-processing
https://datascientest.com/nlp-word-embedding-word2vec

= compréhension, manipulation et génération du langage naturel par les machines

Exemples d'utilisation : traduction, classification de texte, analyse de sentiments, chatbot, etc. 

Généralement 2 aspects

### 1. Linguistique 

= prétraiter et transformer le texte en entrée pour avoir un jeu de données exploitable (nettoyage du texte, normalisation des données, transformation en données numériques)

### Normalisation des données

* **Tokenisation** = découpage du texte en plusieurs pièces appelés tokens. Ex. : « Vous trouverez en pièce jointe le document en question » -> « Vous », « trouverez », « en pièce jointe », « le document », « en question ».
* **Stemming** = découper la fin des mots dans afin de ne conserver que la racine du mot. Ex. : « trouverez » -> « trouv ».
* **Lemmatisation** = similaire au stemming, mais plus "sophistiqué", supprime uniquement les terminaisons inflexibles et isole la forme canonique du mot (=le lemme). Ex. : « trouvez » -> trouver.
* Autres opérations : suppression des chiffres, ponctuation, symboles et stopwords, passage en minuscule, etc..


#### Représenter les mots sous forme numérique

Premières solutions NLP : dictionnaires de listes d'ensembles de synonymes et hypernimes (relation 'est un') (par ex. WordNet) ; ex. : ; plusieurs limitations : pas de nuance, incapacité à prendre en compte le contexte, pas à jour, etc..

Vecteurs one-hot (*one-hot vector*) : vecteur binaire, aussi grand que le nombre de mots dans le dictionnaire ; ex. de limitations : vecteurs orthogonaux (ne peut pas capturer la similarité), vecteurs aussi longs que le dictionnaire de mots

Vecteurs de mot (*word vectors* = *embeddings*) : 
* obtenir pour chaque mot un vecteur dense => **représentation distribuée** (*distributed representation*) 
* métriques pour mesurer similarité entre 2 mots, par ex. *cosine similarity* (angle entre les vecteurs) ou produit scalaire (angle et magnitude des vecteurs)
* réduire la dimension pour capturer le contexte
* l'*embedding* d'un mot correspond au résultat que retourne une couche dense (= multiplier la matrice d'*embedding* par la représentation one-hot du mot
* méthode la plus utilisée : **Word2vec**
  - entrainement non supervisé
  - réseau de neurones à 3 couches (1 couche d’entrée, 1 couche cachée, 1 couche de sortie)
  - le résultat de la couche cachée est la nouvelle représentation du mot
  - 2 variantes 
      1. Common Bag Of Words = nourri par le contexte, prédit le mot cible
      2. Skip Gram = nourri par le mot cible, et prédit les mots du contexte



2. Apprentissage automatique : appliquer des modèles d'apprentissage automatique ou profond à ce jeu de données

### Large Language Models (LLMs)

#### LLMs open source

il existe d'autres modèles de langage génératifs qui peuvent être utilisés comme alternatives à ChatGPT. Par exemple, des modèles Open Source tels que Falcon-40b-instruct, Guanaco-65b-merged, Llama-65b, Alpaca et Vicuna sont disponibles et peuvent être personnalisés pour répondre à des besoins spécifiques.
(ne veut pas dire gratuits ?!)

### Transformers

#### Tokenizers

