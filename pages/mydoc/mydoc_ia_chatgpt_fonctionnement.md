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

ChatGPT is a web app (you can access it in your browser) designed specifically for chatbot applications—and optimized for dialogue. It relies on GPT to produce text, like explaining code or writing poems.  

GPT, on the other hand, is a language model, not an app. (There is an OpenAI playground that lets you play around with GPT, but GPT itself isn't an app.) It can be tailored to build different functions, like text summarizing, copywriting, parsing text, and translating languages. And it has an open API that lets anyone tap into GPT-3 or GPT-4 to build their own AI applications with its functions. It's the brain behind ChatGPT, yes, but it's also the brain behind other tools like Jasper and Writesonic, or Bing's new AI-powered search features.

GPT-3 is the industry standard for language models right now, just like ChatGPT is the industry standard for AI chatbots—and GPT-4 will likely be the standard soon. (Though Google is currently playing catch up with its newly launched chatbot, Bard, using a different language model called LaMDA.) 

What does this mean for integrations?
Even though GPT is a language model and ChatGPT is a chatbot, they each have their own open API,

Generative Pre-trained Transformer

ChatGPT est un **modèle de langage**, avec une architecture basée sur les transformers

ChatGPT 4 est **multimodal** ; chaque modalité doit être convertie dans une représentation dans le même espace d'*embedding*

https://medium.com/@amol-wagh/whats-new-in-gpt-4-an-overview-of-the-gpt-4-architecture-and-capabilities-of-next-generation-ai-900c445d5ffe

https://the-decoder.com/gpt-4-architecture-datasets-costs-and-more-leaked/
GPT-4 The key points:

GPT-4's Scale: GPT-4 has ~1.8 trillion parameters across 120 layers, which is over 10 times larger than GPT-3.
Mixture Of Experts (MoE): OpenAI utilizes 16 experts within their model, each with ~111B parameters for MLP. Two of these experts are routed per forward pass, which contributes to keeping costs manageable.
Dataset: GPT-4 is trained on ~13T tokens, including both text-based and code-based data, with some fine-tuning data from ScaleAI and internally.
Dataset Mixture: The training data included CommonCrawl & RefinedWeb, totaling 13T tokens. Speculation suggests additional sources like Twitter, Reddit, YouTube, and a large collection of textbooks.
Training Cost: The training costs for GPT-4 was around $63 million, taking into account the computational power required and the time of training.
Inference Cost: GPT-4 costs 3 times more than the 175B parameter Davinci, due to the larger clusters required and lower utilization rates.
Inference Architecture: The inference runs on a cluster of 128 GPUs, using 8-way tensor parallelism and 16-way pipeline parallelism.
Vision Multi-Modal: GPT-4 includes a vision encoder for autonomous agents to read web pages and transcribe images and videos. The architecture is similar to Flamingo. This adds more parameters on top and it is fine-tuned with another ~2 trillion tokens.

OpenAI GPT-4 is said to be based on the Mixture of Experts architecture and has 1.76 trillion parameters.

GPT-4 is rumored to be based on eight models, each with 220 billion parameters, which are linked in the Mixture of Experts (MoE) architecture. 

https://neuroflash.com/blog/gpt-4-wiki/
Enhanced language capabilities and improved performance: One of the remarkable features of GPT-4 lies in its ability to generate creative and coherent text. Thanks to its advanced language modeling techniques, the model can produce human-like responses, making it an invaluable tool for content creation, chatbots, and virtual assistants. GPT-4’s impressive neural network architecture allows it to understand context, grasp nuances, and provide accurate and meaningful outputs.
Larger contextual window: GPT-4 possesses an advanced neural network architecture that allows it to understand more context, nuances, and provide meaningful outputs.
Multimodal content: GPT-4 can process multi-modal content, including text, images, music, and more, opening up possibilities for applications in marketing, entertainment, and virtual reality.
Improved knowledge acquisition: It showcases improved knowledge acquisition and reasoning abilities, comprehending complex information, handling ambiguous queries, and delivering precise answers.
Bigger data base: GPT-4 leverages vast amounts of data available on the internet to provide well-informed insights.

## NLP

https://datascientest.com/introduction-au-nlp-natural-language-processing
https://datascientest.com/nlp-word-embedding-word2vec
https://web.stanford.edu/class/cs224n/slides
http://web.stanford.edu/class/cs224n/readings
http://colah.github.io/posts/2015-08-Understanding-LSTMs

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


* **Gated Recurrent Units (GRUs)** : RNNs vus jusqu'ici passent d'un état caché au suivant par transformation affine et non-linéarité ponctuelle (*point-wise nonlinearity*) ; les GRUs représentent une modification de l'architecture des RNNs, avec l'utilisation d'une fonction d'activation *gated* (*gated activation function*); grâce à leur mémoire plus persistante, les GRUs permettent de capturer les dépendances à long terme

![GRU (vue mathématique)](../../images/GRU_math.png "GRU - math").

1. <u>New memory generation</u> : consolidation of a new input word with the past hidden state (=combining a newly observed word with the past hidden state to summarize this new word in light of the contextual past)
2. <u>Reset Gate</u> : determining how important previous hidden state is to the summarization of the new memory, if it is totally irrelvant for the computation of the new memory, can completely diminish past hidden state 
3. <u>Update Gate</u> : determining how much of previous hidden state should be carried forward to the next state (=1 if almost entirely copied out, =0 new memory mostly forwarded to the next hidden state)
4. <u>Hidden state</u> : finally generated using the past hidden input and the new memory generated with advice of the update gate

![GRU (vue interne)](../../images/GRU_details.png "GRU - détails"). to train a GRU, we need to learn all the different parameters: W, U, W<sup>(r)</sup>, U<sup>(r)</sup>, W<sup>(z)</sup>, U<sup>(z)</sup>

* **Long-Short-Term-Memories** : même motivation que les GRUs, diffèrent légèrement

![LST (vue détaillée)](../../images/LSTM_details.png "LSTM - détails").

We can gain intuition of the structure of an LSTM by thinking of its
architecture as the following stages:
1. New memory generation : analogous to memory generation stage in GRUs
2. Input Gate: new memory generation stage doesn't check if the new word is even important before generating the new memory – this is exactly the input gate's function. Uses input word and past hidden state to **determine whether or not the input is worth preserving** and thus is used to gate the new memory. Produces it as an indicator of this information.
3. Forget Gate: similar to the input gate except that does not make a determination of usefulness of the input word – instead makes an assessment on **whether the past memory cell is useful** for the computation of current memory cell. Looks at the input word and the past hidden state.
4. Final memory generation: first takes the advice of the forget gate and accordingly **forgets the past memory**; similarly, takes the advice of the input gate and accordingly **gates the new memory**; then **sums these 2 results** to produce the **final memory**
5. Output/Exposure Gate: gate that does not explicitly exist in GRUs. Purpose : **separate the final memory from the hidden state**. Final memory contains a lot of information not necessarily required to be saved in the hidden state. Hidden states are used in every single gate of an LSTM and thus, this gate makes the assessment regarding **what parts of the memory needs to be exposed/present in the hidden state**. The signal it produces to indicate this is used to **gate the point-wise tanh of the memory**.

* *Long Short-Term Memory RNNs (LSTMs)* : capturer les dépendances longue distance grâce aux ***Gated Recurrent Units (GRU)*** ; à chaque étape *hidden state* et *cell state* (=*long term information*) ; à chaque étape, l'information de la cellule peut être lue/écrasée/écrite en contrôlant 3 ports (*gates* ; = vecteurs de même longueur que ceux des états cachés et de la cellule)
  -  à chaque étape, les éléments d'un *gate* peuvent être ouverts (1) ou fermés (0), ou entre-deux
  -  les *gates* sont dynamiques : leur valeur dépend du contexte actuel
  -  permet la mémoire à long terme (si *forget gate* = 1 et *input gate* = 0 : l'information de la cellule est préservée indéfiniment)
  
![module RNN](../../images/rnn_module.png "Module d'un RNN").
![module LSTM](../../images/lstm_module.png "Module d'un LSTM").
![équations module LSTM](../../images/lstm_module_eq.png "Représentation des équations d'un LSTM").
![légende module](../../images/legende_module.png "légende").
*source : http://colah.github.io/posts/2015-08-Understanding-LSTMs*

* Autres types de RNNs : 
  - RNNs bidirectionels (regarder le contexte à gauche et à droite ; a besoin de la séquence en entier en input) ; ne sont pas des modèles de language (seulement contexte à gauche) 
  - RNNs multi-couches (*multi-layer* ou *stacked* RNNs) : RNNs par définition profond dans 1 dimension (*unrolling* sur plusieurs pas de temps) ; ajouter une dimension supplémentaire en appliquant plusieurs RNNs pour capturer des *higher-level* et *lower-level features* ; les *hidden states* d'une cache sont les inputs de la couche suivante ; sont plus puissants mais requièrent des *skip connections*

Traduction avec les RNNs : combiner 2 RNNs (*encoder RNN* qui encode la séquence source et *decoder RNN* qui génère la sentence *conditioned on encoding*

#### Attention
https://machinelearningmastery.com/the-attention-mechanism-from-scratch/
https://machinelearningmastery.com/what-is-attention/

Goulot d'étranglement lors de la prédiction *sequence-to-sequence* (*bottleneck problem*)

![Bottleneck problem pour prédictions sequence-to-sequence](../../images/bottleneck_problem.png "Bottleneck problem").
 
-> solution : l'**attention**

Idée centrale : à chaque étape du décodeur, connection directe à l'encodeur pour se concentrer sur une partie particulière de la séquence source

![Attention pour sequence-to-sequence prediction](../../images/attention.png "Attention").

##### A. As introduced by Bahdanau et al. (2014) 

step-by-step computations of:

1) Alignment scores: alignment model takes the encoded hidden states and the previous decoder output to compute a score -> indicates how well the elements of the input sequence align with the current output at the position. The alignment model is represented by a function which can be implemented by a feedforward neural network.

2) Weights: computed by applying a softmax operation to the previously computed alignment scores

3) Context vector: a unique context vector is fed into the decoder at each time step. It is computed by a weighted sum of all encoder hidden states

First implemented an RNN for both the encoder and decoder. 


If we are processing an input sequence of words, then 
1. This will first be fed into an encoder, which will output a vector for every element in the sequence (step 1). 
2. A list of these vectors, together with the decoder’s previous hidden states, will be exploited by the attention mechanism to dynamically highlight which of the input information will be used to generate the output (step 2). 
3. At each time step, the attention mechanism then takes the previous hidden state of the decoder and the list of encoded vectors, using them to generate unnormalized score values that indicate how well the elements of the input sequence align with the current output. Since the generated score values need to make relative sense in terms of their importance, they are normalized by passing them through a softmax function to generate the weights. Following the softmax normalization, all the weight values will lie in the interval [0, 1] and add up to 1, meaning they can be interpreted as probabilities. Finally, the encoded vectors are scaled by the computed weights to generate a context vector (step 3). It is this context vector that is then fed into the decoder to generate a translated output. 

This type of artificial attention is thus a form of iterative re-weighting. Specifically, it dynamically highlights different components of a pre-processed input as they are needed for output generation. This makes it flexible and context dependent.

In a system that does not incorporate attention mechanism, the encoder would generate a fixed-length vector irrespective of the input’s length or complexity. In the absence of a mechanism that highlights the salient information across the entirety of the input, the decoder would only have access to the limited information that would be encoded within the fixed-length vector. This would potentially result in the decoder missing important information. 

The initial attention mechanism can be generalized to process information that can be static and not necessarily related in a sequential fashion, such as in the context of image processing. The attention mechanism can be re-formulated into a general form that can be applied to any sequence-to-sequence task, where the information may not necessarily be related in a sequential fashion. 



##### B. General attention mechanism

3 main components

1. the queries 
2. the keys
3. the values

It performs the following computations:

1. Each query vector is matched against a database of keys to compute a score value. This matching operation is computed as the dot product of the specific query under consideration with each key vector.
2. The scores are passed through a softmax operation to generate the weights.
3. The generalized attention is then computed by a weighted sum of the value vectors, where each value vector is paired with a corresponding key.

 Within the context of machine translation, each word in an input sentence would be attributed its own query, key, and value vectors. These vectors are generated by multiplying the encoder's representation of the specific word under consideration with three different weight matrices that would have been generated during training. 

When the generalized attention mechanism is presented with a sequence of words, it takes the query vector attributed to some specific word in the sequence and scores it against each key in the database. In doing so, it captures how the word under consideration relates to the others in the sequence. Then it scales the values according to the attention weights (computed from the scores) to retain focus on those words relevant to the query. In doing so, it produces an attention output for the word under consideration. 

In summary, the attention mechanism uses a weighted sum of all the encoder hidden states to flexibly focus the attention of the decoder to the most relevant parts of the input sequence. It can be generalized for tasks where the information may not necessarily be related in a sequential fashion.


#### Self-attention
Attention treats each word’s representation as a query to access and incorporate information from a set of values
Attention operates on queries, keys, and values
 self-attention, the queries, keys, and values are drawn from the same source
 attention within a single sentence (not from decoder to encoder).
 
#### Multi-headed attention
https://machinelearningmastery.com/the-transformer-attention-mechanism/
The idea behind multi-head attention is to allow the attention function to extract information from different representation subspaces, which would otherwise be impossible with a single attention head. 



### Transformer

![Transformer - encoder](../../images/transformer_encoder.png "Transformer encoder").

![Transformer - decoder](../../images/transformer_encoder.png "Transformer decoder").

https://pylessons.com/transformers-introduction
https://pylessons.com/transformer-attention
https://pylessons.com/build-transformer

![Transformer](../../images/transformer_pylesson.png "Transformer").
https://heidloff.net/article/foundation-models-transformers-bert-and-gpt/
https://writings.stephenwolfram.com/2023/02/what-is-chatgpt-doing-and-why-does-it-work/
https://peterbloem.nl/blog/transformers
https://medium.com/machine-intelligence-and-deep-learning-lab/transformer-the-self-attention-mechanism-d7d853c2c621
https://towardsdatascience.com/attention-and-transformer-models-fe667f958378


#### LLMs open source

il existe d'autres modèles de langage génératifs qui peuvent être utilisés comme alternatives à ChatGPT. Par exemple, des modèles Open Source tels que Falcon-40b-instruct, Guanaco-65b-merged, Llama-65b, Alpaca et Vicuna sont disponibles et peuvent être personnalisés pour répondre à des besoins spécifiques.
(ne veut pas dire gratuits ?!)

## Self-attention

By 2017, however, the basic strategy to solve
a natural language processing task was to begin with a recurrent
neural network
Issues with RNN 
1) As the sequence gets longer, there is only so much I
can parallelize the computation of the network on a GPU because
of the number of serial dependencies. (Serial meaning one-after-theother) -> cannot leverage power of GPUs (and later, other accelerators like Tensor Processing Units
(TPUs)
2) linear interaction distance. A related issue with RNNs is the difficulty with which distant tokens in a sequence can interact with each
other. By interact, we mean that the presence of one token (already
observed in the past) gainfully affects the processing of another token.
e it can be difficult for networks to precisely
“recall” the presence of a word when a large number of operations
occur after observing that word. This can make it difficult to learn
how distant words should impact the representation of the current
word.

direct interaction between elements of a sequence
might remind you of the attention mechanism [

t, while generating a translation,
we learned how to look back into the source sequence once per token
of the translation.

n entire replacement
for recurrent neural networks just based on attention. This will solve
both the parallelization issues and the linear interaction distance
issues with recurrent neural network


 minimal self-attention architecture
Attention, broadly construed, is a method for taking a query, and
softly looking up information in a key-value store by picking the
value(s) of the key(s) most like the query. By “picking” and “most
like,” we mean averaging overall values, putting more weight on
those which correspond to the keys more like the query. In selfattention, we mean that we use the same elements to help us define
the querys as we do the keys and values.
In this section, we’ll discuss how to develop contextual representations with methods wherein the main mechanism for contextualization is not recurrence, but attention

e many forms of self-attention we’ll discuss  key-query-value self-attention

Our contextual representation hi of xi
is a linear combination (that
is, a weighted sum) of the values of the sequence,
hi =
n
∑
j=1
αijvj
, (7)
where the weights, these αij control the strength of contribution of
each vj
. Going back to our key-value store analogy, the αij softly selects what data to look up. We define these weights by computing the
affinities between the keys and the query, q
⊤
i
kj
, and then computing
the softmax over the sequence:

Intuitively, what we’ve done by this operation is take our element
xi and look in its own sequence x1:n to figure out what information
(in an informal sense,) from what other tokens, should be used in
representing xi
in context.

The self-attention operation has no
built-in notion of the sequence order

In a recurrent
neural network, the order of the sequence defines the order of the
rollout, so two sequences with the same words but in different order have different representations. 
In the
self-attention operation, there’s no built-in notion of order

the representation of a word is not positiondependent; it’s just Ew for whatever word w, and (2) there’s no
dependence on position in the self-attention operations

Position representation through learned embeddings. To represent po-  
sition in self-attention, you either need to (1) use vectors that are
already position-dependent as inputs, or (2) change the self-attention
operation itself. One common solution is a simple implementation
of (1). We posit a new parameter matrix, P ∈ RN×d
, where N is
the maximum length of any sequence that your model will be able to
process.
We then simply add embedded representation of the position of a
word to its word embedding and perform self-attention as we otherwise would. 
Now, the selfattention operation can use the embedding Pi
to look at the word at
position i differently than if that word were at position j. This is done,
e.g., in the BERT paper

Position representation through changing α directly. Instead of changing the input representation, another thing we can do is change
the form of self-attention to have a built-in notion of position. One
intuition is that all else held equal, self-attention should look at
“nearby” words more than “far” words. Attention with Linear Biases
[Press et al., 2022] is one implementation of this idea
the bias
we add makes attention focus more on nearby words than far away
words, all else held equal.

Imagine if we were to stack self-attention layers. Would this be
sufficient for a replacement for stacked LSTM layers? Intuitively,
there’s one thing that’s missing: the elementwise nonlinearities that
we’ve come to expect in standard deep learning architectures
 stacking 2 self-attention layers is just a linear
combination of a linear transformation of the input, much like a
single layer of self-attention

In practice, after a layer of self-attention, it’s common to apply
feed-forward network independently to each word representation:

often the hidden
dimension of the feed-forward network is substantially larger than
the hidden dimension of the network, d—this is done because this
matrix multiply is an efficiently parallelizable operation, so it’s an
efficient place to put a lot of computation and parameters

Future masking
language modeling so far (autoregressive modeling)
One crucial aspect of this process is that we can’t look at the future
when predicting it—otherwise the problem becomes trivial. This idea
is built-in to unidirectional RNNs (d by the rollout of the RNN, we haven’t looked at the future.)

In a Transformer, there’s nothing explicit in the self-attention
weight α that says not to look at indices j > i when representing
token i. In practice, we enforce this constraint simply adding a large
negative constant to the input to the softmax (or equivalently, setting
αij = 0 where j > i.)

4
It might seem like one should use −∞
as the constant, to “really” ensure that
you can’t see the future. However, this
is not done; a modest constant within
even the float range of the ‘float16‘
encoding is used instead, like −105
.
Using infinity can lead to NaNs and
it’s sort of undefined how each library
should treat infinite inputs, so we tend
to avoid using it. And because of finite
precision, a large enough negative
constant will still set the attention
weight to exactly zero

summary: Our minimal self-attention architecture has (1) the self-attention
operation, (2) position representations, (3) elementwise nonlinearities,
and (4) future masking (in the context of language modeling.)

#### Transformer

 as of 2023, by far the most-used architecture in NLP is called
the Transformer, introduced by [Vaswani et al., 2017] much more components in addition to self-attention

The Transformer is an architecture based on self-attention that consists of stacked Blocks, each of which contains self-attention and feedforward layers, and a few other components


##### multi-head self-attention

a single call of self-attention is best at picking out a single
value (on average) from the input value set. It does so softly, by
averaging over all of the values, but it requires a balancing game in
the key-query dot products in order to carefully average two or more
things

multi-head self-attention,
intuitively applies self-attention multiple times at once, each with
different key, query, and value transformations of the same input,
and then combines the outputs

 self-attention is performed with each head
 we define the output of multi-head self-attention as a linear
transformation of the concatenation of the head outputs

When we perform multi-head self-attention in this matrix form,
 reshape matrix shape
 splitting the model dimensionality into two axes, for the
number of heads and the number of dimensions per head.

he output
of each head is in reduced dimension d

perform the batched softmax operation in parallel across the
heads, using the number of heads kind of like a batch axis (and
indeed in practice we’ll also have a separate batch axis.) So, the
total computation (except the last linear transformation to combine
the heads) is the same, just distributed across the (each lower-rank)
heads.

a diagram like the single-head diagram, demonstrating
how the multi-head operation ends up much like the single-head
operation :

#### Layer Norm

 One important learning aid in Transformers is layer normalization
[Ba et al., 2016]. The intuition of layer norm is to reduce uninformative variation in the activations at a layer, providing a more stable
input to the next layer. Further work shows that this may be most
useful not in normalizing the forward pass, but actually in improving
gradients in the backward pass

To do this, layer norm (1) computes statistics across the activations
at a layer to estimate the mean and variance of the activations, and (2)
normalizes the activations with respect to those estimates, while (3)
optionally learning (as parameters) an elementwise additive bias and
multiplicative gain by which to sort of de-normalize the activations
in a predictable way. The third part seems not to be crucial, and may
even be harmful [Xu et al., 2019], so we omit it

statistics
computed independently for a single index into the sequence length
(and a single example in the batch) and shared across the d hidden
dimensions. Put another way, the statistics for the token at index i
won’t affect the token at index j ̸= i

##### Residual Connections
residual connections simply add the input of a layer to the output of
that layer

the intuition being that (1) the gradient flow of the identity function
is great (the local gradient is 1 everywhere!) so the connection allows
for learning much deeper networks, and (2) it is easier to learn the
difference of a function from the identity function than it is to learn
the function from scratch

useful in DL in general, not only Tansformers

, the application of layer normalization and residual connection
are often combined in a single visual block labeled Add & Norm

A VERIFIER
pre-normalization : layer normalization then residual connection
or post-normalization : residual connection added then LN

It turns out that the gradients
of pre-normalization are much better at initialization, leading to
much faster training

##### Attention logit scaling

Another trick introduced in [Vaswani et al., 2017] they dub scaled dot
product attention.

The intuition of scaling is that, when
the dimensionality d of the vectors we’re dotting grows large, the dot
product of even random vectors (e.g., at initialization) grows roughly
as √
d. So, we normalize the dot products by √
d to stop this scaling:

##### ransformer Encoder
A Transformer Encoder takes a single sequence w1:n, and performs
no future masking. It embeds the sequence with E to make x1:n, adds
the position representation, and then applies a stack of independently
parameterized Encoder Blocks, each of which consisting of (1) multihead attention and Add & Norm, and (2) feed-forward and Add &
Norm. So, the output of each Block is the input to the next

In the case that one wants probabilities out of the tokens of a
Transformer Encoder (as in masked language modeling for BERT
[Devlin et al., 2019], which we’ll cover later), one applies a linear
transformation to the output space followed by a softmax.

Uses of the Transformer Encoder. A Transformer Encoder is great in
contexts where you aren’t trying to generate text autoregressively
(there’s no masking in the encoder so each position index can see
the whole sequence,) and want strong representations for the whole
sequence (again, possible because even the first token can see the
whole future of the sequence when building its representation.)

##### Transformer Decoder
To build a Transformer autoregressive language model, one uses a
Transformer Decoder. These differ from Transformer Encoders simply
by using future masking at each application of self-attention. This
ensures that the informational constraint (no cheating by looking at
the future!) holds throughout the architecture. We show a diagram
of this architecture in Figure 4. Famous examples of this are GPT2 [Radford et al., 2019], GPT-3 [Brown et al., 2020] and BLOOM
[Workshop et al., 2022].

##### Transformer Encoder-Decoder
A Transformer encoder-decoder takes as input two sequences. Figure 6 shows the whole encoder-decoder structure. The first sequence
x1:n is passed through a Transformer Encoder to build contextual
representations. The second sequence y1:m is encoded through a
modified Transformer Decoder architecture in which cross-attention
(which we haven’t yet defined!) is applied from the encoded representation of y1:m to the output of the Encoder. So, let’s take a quick
detour to discuss cross-attention; it’s not too different from what
we’ve already seen.

##### Cross-Attention. Cross-attention uses one sequence to define the
keys and values of self-attention, and another sequence to define
the queries.

we have some intermediate representation h
(y) of sequence y1:m,
then we let the queries come from the decoder (the h
(y)
sequence)
while the keys and values come from the encoder:

in the Transformer Encoder-Decoder, crossattention always applies to the output of the Transformer encode

Uses of the encoder-decoder. An encoder-decoder is used when we’d
like bidirectional context on something (like an article to summarize) to build strong represenations (i.e., each token can attend to
all other tokens), but then generate an output according to an autoregressive decomposition as we can with a decoder. While such
an architecture has been found to provide better performance than
decoder-only models at modest scale [Raffel et al., 2020], it involves
splitting parameters between encoder and decoder, and most of the
largest Transformers are decoder-only

#### Tokenizers


