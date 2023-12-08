---
title: ChatGPT - prompt engineering et bonnes pratiques
keywords: IA, IT, ChatGPT
last_updated: July 3, 2016
tags: [IA]
summary: "Conseils de prompt engineering"
sidebar: mydoc_sidebar
permalink: ChatGPT_promptEngineering.html
folder: mydoc
---

*Sources*
* "[ChatGPT en entreprise](https://outilia.fr)" de Matthieu Corthésy

## Eléments-clés du prompt

* contexte
* rôle
* cheminement à suivre
* cadrage et contraintes

## Méthode ACTIF-VE développée par M. Corthésy

7 éléments pour un prompt de qualité, leur ordre n'est pas important :

1.	**action** = la tâche que ChatGPT doit effectuer
  - demander plusieurs réponses possibles plutôt qu'une solution
  - être très directif pour éviter qu'il s'égare par rapport à nos attentes

3.	**contexte** = donner le plus d'informations possible sur nos attentes
  -	donner des exemples, des modèles/méthodes à suivre, des bonnes pratiques
  -	contraintes : public cible, longueur, nombre de mots, manière de traiter le sujet, genre et style, éléments à prendre en compte, sujet, etc.)
  -	enjeux (problématique) et objectifs  de la demande)
  -	spécifier des mots clés (termes spécifiques devant être utilisés)

3.	**tonalité** = style attendu de la réponse
  -	créatif : métaphorique / storyteller / optimiste / empathique / passionné / créatif
  -	professionnel : ifnormatif / professinnel / formel / persuasif / explicatif / concis
  -	critique : direct / critique / sincère / examinateur / cyniqu e/ rugueux 
  -	analytique : factuel / logique / objectif / précis / rigoureux / data-driven

4.	**identité** = rôle à suivre (débutant / expert / ...)
  -	souvent mis en début de prompt  
  - attention au choix des mots (éviter "act as marketing expert" (=prétendre), préférer "tu es un expert marketing")

5.	**format** = résultat attendu
  - liste, tableau, markdown, contenu PowerPoint
  - guide d'utilisation, plan de formation
  - analyse SWOT, FAQ, discours, quizz, script, roadmap

6. **validation** (amélioration) et 7. **étapes** (processus)
  - faire répondre à la question de départ en plusieurs étapes, décrites une à une dans le prompt, avec une validation avant de passer à la suivante (limite de mémoire : si besoin rappeler les éléments principaux de la discussion) 
  - ex. : "Tu suivras 4 étapes. A la fin de chaque étape tu me poseras des questions pour améliorer ta réponse et tu me demanderas si je valide l'étape. Ensuite, tu passeras à l'étape suivante quand je te dirai : OK. Etape 1 : tu vas me demander [...] ; Etape 2 [...]".


## Se prémunir des hallucinations

* Cadrer les demandes, imposer un contexte et des contraintes (éviter les questions ouvertes et vagues)
* Demander de poser de question pour l'aider à cibler la réponse (ex. "... Pose-moi des questions sur notre produit avant de répondre.")
* S'enquérir de l'exactitude ; "es-tu sûr de l'exactitude de ta réponse ?" pour le forcer à analyser la réponse et indiquer là où il n'est pas certain

## Eviter l'oubli

Nombre de tokens que ChatGPT peut traiter est limité ; plus la conversation avance, plus il oublie le début de la conversation

* Demander de résumer les points clés de la discussion
* Rappeler les points essentiels du contexte
* Démarrer une nouvelle conversation en indiquant les éléments de contexte dont il a besoin

## Utiliser les *Custom Instructions*

* Disponible dans Paramètres (Settings)/Fonctionnalités bêta (Beta features)
* Permet de spécifier un contexte comme base pour toutes les conversations (sans devoir le remettre à chaque nouvelle discussion)



{% include links.html %}
