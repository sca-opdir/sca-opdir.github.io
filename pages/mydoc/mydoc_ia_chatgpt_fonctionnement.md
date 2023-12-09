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
https://web.stanford.edu/class/cs224n/slides/cs224n-2021-lecture01-wordvecs1.pdf
http://web.stanford.edu/class/cs224n/readings/cs224n-2019-notes01-wordvecs1.pdf
http://web.stanford.edu/class/cs224n/readings/cs224n-2019-notes02-wordvecs2.pdf
http://web.stanford.edu/class/cs224n/slides/cs224n-2021-lecture02-wordvecs2.pdf

= compréhension, manipulation et génération du langage naturel par les machines

Exemples d'utilisation : traduction, classification de texte, analyse de sentiments, chatbot, etc. 

Généralement 2 aspects

### 1. Linguistique 

= prétraiter et transformer le texte en entrée pour avoir un jeu de données exploitable (nettoyage du texte, normalisation des données, transformation en données numériques)

#### Normalisation des données

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
* 2 catégories de méthodes : *SVD-based* (*count-based*; *embeddings* donnés par la matrice unitaire d'une décomposition en valeurs singulières d'une matrice de co-occurence ; 1x/dataset) et *iteration-based* (l'*embedding* correspond aux paramètres du modèle, qui est entrainé par optimisation d'une fonction objectif ; 1 mot à la fois)
* méthode la plus utilisée : **Word2vec** (*iteration based*)
  - entrainement non supervisé
  - réseau de neurones à 3 couches (1 couche d’entrée, 1 couche cachée, 1 couche de sortie)
  - le résultat de la couche cachée est la nouvelle représentation du mot
  - 2 variantes 
      1. Common Bag Of Words = nourri par le contexte, prédit le mot cible
      2. Skip Gram = nourri par le mot cible, et prédit les mots du contexte
* **GloVe** : combine les 2 types de méthodes *global matrix factorization* (*count-based*) + *local context window* ; les premières capturent bien la similarité des mots, mais mal les analogies ; les deuxièmes capturent des motifs linguistiques complexes au-delà de la similarité, mais n'utilisent pas les statistiques de co-occurence globales -> *weighted least squares model* entrainé sur les occurences globales,  utilise statistiques globales pour prédire la probabilité d'un mot d'apparaitre dans le contexte d'un autre mot


### 2. Apprentissage automatique : appliquer des modèles d'apprentissage automatique ou profond à ce jeu de données

Modèles de language (*language model*, *LM*) pour prédire le mot suivant


* modèles *n-gram* (*n-gram* = groupe de *n* mots consécutifs; ex. : "les étudiants" est un bigramme) : statistiques sur la fréquence des différents *n-grams* pour prédire le prochain mot (comparaison entre l'occurence de chaque *n-gram* par rapport à la fréquence de chaque mot ; 2 problèmes principaux : *sparsity* et *storage*
* *fixed-window neural Language Models* : pas de problème de *sparsity* ni de stockage des *n-grams* ; limites : taille de la fenêtre limitée et fixe ; différents poids sont appliqués pour chaque mot (pas de symétrie dans la façon dont ils sont traités)
* *Recurrent Neural Networks (RNN)* : appliquer toujours les mêmes poids (symétrie), la taille du modèle n'augmente pas avec l'augmentation de la taille du contexte, peut regarder en arrière (conditionner le modèle sur tous les mots précédents); limites : lenteur pour le calcul, difficulté à regarder loin derrière (*vanishing and exploding gradients*); peut aussi être entrainé pour prédire le prochain caractère (*character-level RNN-LM*) ; usages : tagging, analyse de sentiments, traduction, etc.

![architecture d'un RNN simple](../../images/simple_RNN.png "RNN simple").

*source : http://web.stanford.edu/class/cs224n/slides/cs224n-2021-lecture06-fancy-rnn.pdf*

* *Long Short-Term Memory RNNs (LSTMs)* : capturer les dépendances longue distance grâce aux ***Gated Recurrent Units (GRU)*** ; à chaque étape *hidden state* et *cell state* (=*long term information*) ; à chaque étape, l'information de la cellule peut être lue/écrasée/écrite en contrôlant 3 ports (*gates* ; = vecteurs de même longueur que ceux des états cachés et de la cellule)
  -  à chaque étape, les éléments d'un *gate* peuvent être ouverts (1) ou fermés (0), ou entre-deux
  -  les *gates* sont dynamiques : leur valeur dépend du contexte actuel
  -  permet la mémoire à long terme (si *forget gate* = 1 et *input gate* = 0 : l'information de la cellule est préservée indéfiniment)
  
![module RNN](../../images/rnn_module.png "Module d'un RNN").

![module LSTM](../../images/lstm_module.png "Module d'un LSTM").

![équations module LSTM](../../images/lstm_module_eq.png "Représentation des équations d'un LSTM").

![légende module](../../images/legende_module.png "légende").

* Autres types de RNNs : 
  - RNNs bidirectionels (regarder le contexte à gauche et à droite ; a besoin de la séquence en entier en input) ; ne sont pas des modèles de language (seulement contexte à gauche) 
  - RNNs multi-couches (*multi-layer* ou *stacked* RNNs) : RNNs par définition profond dans 1 dimension (*unrolling* sur plusieurs pas de temps) ; ajouter une dimension supplémentaire en appliquant plusieurs RNNs pour capturer des *higher-level* et *lower-level features* ; les *hidden states* d'une cache sont les inputs de la couche suivante ; sont plus puissants mais requièrent des *skip connections*
  
 

### Large Language Models (LLMs)

#### LLMs open source

il existe d'autres modèles de langage génératifs qui peuvent être utilisés comme alternatives à ChatGPT. Par exemple, des modèles Open Source tels que Falcon-40b-instruct, Guanaco-65b-merged, Llama-65b, Alpaca et Vicuna sont disponibles et peuvent être personnalisés pour répondre à des besoins spécifiques.
(ne veut pas dire gratuits ?!)

### Transformers

#### Tokenizers

