---
title: ChatGPT - les GPTs personnalisés
keywords: IA, IT, ChatGPT
last_updated: January 23, 2025
tags: [IA, chatGPT]
summary: "ChatGPT: customGPTs"
sidebar: mydoc_sidebar
permalink: ChatGPT_custom.html
folder: mydoc
---

*Sources:*
* "[ChatGPT en entreprise](https://outilia.fr)" de Matthieu Corthésy
* https://www.01net.com/actualites/plugins-chatgpt-extensions-tout-savoir.html 
https://autogpt.net/top-10-chat-gpt-plugins/
* trouver des plugins et des GPTs https://www.whatplugin.ai/
* [cours](https://acoustic-licorice-c24.notion.site/4-Que-sont-les-GPTs-10-exemples-4a332e3d18374515b838975848a3220e) et [blog](https://academieweb3.com/gpts/) de J.-B. Berthoux
  
## ChatGPT 4.0

Par rapport à GPT-3.5 : multi-modal, plus de mémoire, plus long contexte, meilleure compréhension, meilleure qualité et précision des résultats mais plus de paramètres, plus lent, plus polluant


## Les GPTs

### Créer des GPTs personnalisés

![créer un GPT personnalisé](../../images/customGPT_cheatsheet.jpg "Créer un GPT")
([source](https://acoustic-licorice-c24.notion.site/4-Que-sont-les-GPTs-10-exemples-4a332e3d18374515b838975848a3220e))

Permet de créer des persona ; les voir comme des stagiaires.

En entreprise : soit créer 1 GPT qui correspond à chaque type de poste ; ou créer 1 GPT par tâche

Limites:
- même en ajoutant des documents de référence, les GPTs continuent à inventer des faits ; parfois, ils ne se basent pas sur les documents ajoutés pour répondre (bien rédiger les prompts !)
- GPT-4o a une mémoire de 128 000 tokens soit 300 pages de livre mais des tests ont montré que la mémoire fléchissait à partir de 73 000 tokens.
- les GPTs accepteraient seulement 20 documents

GPTs are custom versions of ChatGPT that users can tailor for specific tasks or topics by combining instructions, knowledge, and capabilities.

Knowledge: allows you to upload files to give your GPT additional context beyond what the GPT-4 Turbo model already has
Custom actions: For details, see the section on Connecting GPTs to third-party applications in this article or check the API documentation.

https://openai.com/blog/introducing-gpts 

https://www.whatplugin.ai/ (plugins et GPTs)

concevant des modèles plus spécialisés pour des domaines et des tâches plus spécifiques
démarrer une conversation avec le GPT Builder en lui expliquant ce que vous attendez de lui.

Donnez-lui un nom et une description pour votre futur GPT, puis des instructions. Sélectionnez ensuite les fonctionnalités ChatGPT que vous souhaitez que votre GPT personnalisé possède. Par exemple, la navigation sur le web, la génération d’images par le biais de DALL-E ou des compétences en matière de codage.

Vous pouvez même intégrer des données du monde réel pour connecter votre GPT à une base de données externe, à une boîte de réception ou à un site d’e-commerce.
https://www.zdnet.fr/guide-achat/avec-chatgpt-creez-vos-propres-gpt-personnalises-39962626.htm


### Utiliser les GPTs personnalisés

Commencer une conversation avec un GPT

Appeler différents GPTs avec "@" dans une même conversation

### Exemples de GPTs 

- [Whimsical Diagrams](https://chatgpt.com/g/g-vI2kaiM9N-whimsical-diagrams) : outil de visualisation (mind map, diagramme de Flux, etc.)
- [Tree Of Thoughts](https://chatgpt.com/g/g-LVXSGJ1VN-tree-of-thoughts) : demander à 3 experts de donner une perspective sur une problématique métier
- [Anna - Instructions personnalisées](https://chatgpt.com/g/g-XRHm1CIvc-anna-instructions-personnalisees) : aide à la rédaction d'instructions personnalisées pour GPT (configuration "Customize ChatGPT")

Lien : 

### Custom GPTs pour l'OPDir

##### Custom GPTs publics

* GPT pour la [procédure de demande d'inscription tardive] (https://chatgpt.com/g/g-tYZM6JJj2-sca-insc-tardive)

* GPT avec les [principales ordonnances (OPD, OTerm, OCCEA, OSIAgr)](https://chatgpt.com/g/g-x7lHJPugN-sca-oterm-osiagr-occea-opd-2024)

* GPT avec les [ordonnances Bio](https://chatgpt.com/g/g-hzozo3blj-sca-ordonnances-bio-obio-oab-oafg-oab-defr)

* GPT avec le contenu spécifique de l'OPD pour les contributions à la [biodiversité](https://chatgpt.com/g/g-9pMPLGz8o-sca-opd-biodiversite), au [bien-être animal](https://chatgpt.com/g/g-QL8136ho3-sca-opd-bien-etre-animal) et les [PER](https://chatgpt.com/g/g-7Bt0Fxb1v-sca-opd-per)

* GPT sur [l'agriculture et la biodiversité](https://chatgpt.com/g/g-5HdBQh98j-sca-agriculture-et-biodiversite) (fiches Agridea)

* GPT sur les [marchés publics](https://chatgpt.com/g/g-67875d1a76c081919e72ecf74af52ec5-sca-marches-publics) 

##### Custom GPTs internes

* génération requête SQL pour données export GDM & parsing du retour

### Autres GPTs publics 

faire une recherche google :
site:chat.openai.com/g/ "mot-clé"

Quelques exemples : 

1. GPT Finder
https://chat.openai.com/g/g-RuhDS8mbd

When Custom GPT was launched a few weeks ago, I struggled to find the best GPTs. So, what to do? Well, I came up with the idea to build a Custom GPT that searches OpenAI's database of GPTs.

This GPT allows you to search across all public GPTs in one place and ranks them based on popularity. Moreover, every day, hundreds of new amazing GPTs join the ranks!

* Scholar AI
* Data Analysis
ConvertAnything is a specialized GPT designed to handle file conversions with efficiency and precision

Grimoire is a highly specialized AI designed to assist with coding and programming tasks. It meticulously analyzes requirements, plans solutions in detail, and writes bug-free, fully functional, and efficient code. This AI prioritizes readability in code, ensures mobile-friendly design, and caters to both advanced programmers and beginners seeking guidance.

Canva is a specialized chatbot designed to assist users in creating visually appealing designs using Canva's user-friendly platform.
Zapier - Get the power of Zapier's 6,000+ apps directly in your custom GPT.


