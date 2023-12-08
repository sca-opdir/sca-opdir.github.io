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
  - ex. : "Tu suivras 4 étapes. A la fin de chaque étape tu me poseras des questions pour améliorer ta réponse et tu me demanderas si je valide l'étape. Ensuite, tu passeras à l'étape suivante quand je te dirai : OK. Etape 1 : tu vas me demander ... ; Etape 2 ...".

## Rebondir sur la réponse de ChatGPT (message de suivi)

* Une fois la réponse obtenue, relancer avec une autre question
* Ex. : faire faire un tableau avec les caractéristiques principales des concurrents puis follow-up message "tu es un commercial expert [...] ; sur la base des informations récoltées dans le tableau sur les concurrents, trouve les faiblesses de chaque concurrent ... utilise ton analyse pour établir une stratégie ... "

## Amélioration continue du prompt

* Passer dans un mode itératif et améliorer continuellement le prompt selon les besoins spécifiques 
* ChatGPT révise le prompt à chaque étape
* Attention à la limitation de la mémoire (rappeler les éléments clés de la discussion si besoin)


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

## Mots-types pour construire un prompte

[rôle] [action] [but/résultat souhaité] [contrainte/affinement]

**rôle** : [Tu es/agis comme/Joue le rôle de] [analyste/conseiller en/responsable de [...]/expert/technicien de [...]/spécialiste/responsable de/coach/superviseur de/formateur en/analyste de/consultant/évaluateur de/professeur de/générateur d'idées/outil de [recherche de prospects]/[nom de métier]] [pour une entreprise de .../ avec une expertise sur ...]

**action** : propose / réalise / estime / crée / aides à [formuler/créer/préparer/élaborer/me préparer pour ...] pour [une start-up qui ...] / identifie / évalue [la performance] / élabore / rédige / donne / formule / mène / génère / développe /écris / cartographie [le parcours ...] / énumère / prépare / utilise [l'analyse SWOT] pour concevoir / examine [notre proposition/ce site web] et suggère [des façons de l'améliorer pour la rendre plus ...] / conçois / fournis / analyse [le parcours/une crise récente ...] / examine [le CV pour ...] et évalue / élabore / présente / suggère / effectue / guide [le client à travers le processus] / conçois / imagine / explique [comment [notre site] devrait gérer [...] pour [...]/comment implémenter/les différences/les avantages/les meilleures pratiques pour .../pourquoi [...] serait] / partage [des astuces ...]/ donne [des conseils sur/une liste de .../une analyse détaillée de/des recommandations/...] / traduis / mets l'accent [sur les différences de ...] / discute [des avantages...] / décris [comment baliser correctement un article]/révise et édite [... pour le rendre plus ...] / corrige [les erreurs de grammaire et de style] / révise [cet article pour le rendre plus fluide et engageant] / définis [trois objectifs] / identifie et décris [le profil de ...] / recommande / identifie et évalue les risques / évalue [la qualité de] / communique

**résultat souhaité** : [5] idées [uniques/pour une campagne de...] / analyse [SWOT/de concurrence/de la performance/des risques/d'écart] / étude [sur le marché/de cas client] / demande potentielle / énoncé de mission / risques / stratégie [de négociation/prospection] / plan [financier/de community management/de contenu/de campagne/de formation/de vente/de cours/d'action/de gestion de crise] / un communiqué / un pitch / résumé exécutif convaincant / évaluation [approximative/annuelle de ... pour ...] / recommandations / solutions [pour résoudre ce problème] / une liste / une série de messages [de suivi pour ...] / un script [pour un webinaire/un podcast/une vidéo [explicative]/une publicité de [...] minutes sur le fonctionnement de/qui explore/explique ...] / les principaux points à prendre en compte / les réponses [aux objections possibles / à [3] types de commentaires] / un scénario de [...] / une réponse [étape par étape/qui reconnait le problème et [...]/détaillée à ...] / techniques de persuasion [efficaces que nous pourrions utiliser pour ...] / e-mail [pour informer de [...]/promotionnel/de suivi/de marketing/de bienvenue/de relance/d'invitation pour/à ...] / notre processus [de vente] / une réponse [empathique et résolutive à ...] / [3] améliorations significatives qui pourraient [rendre l'expérience plus ...] / enquête [de satisfaction] / offre d'emploi / résumé détaillé / une série de [10] questions [pour un entretien] / lettre [de bienvenue/d'appréciation/de rejet respectueuse et encourageante pour ...] / un plan [de projet/de contingence/de formation/de cours/de communication/d'amélioration pour ...] / un feedback [de performance pour ...] / un parcours [de carrière pour ...] / un guide [détaillé sur [...]/complet sur [...]/étape par étape/de formation/d'intégration pour ...] / des zones d'amélioration [et des recommandations pour ...] / des initiatives [à mettre en place pour ...] / une approche pour [...] / un questionnaire [de satisfaction/d'évaluation] / une politique [d'équité] / [5] légendes [engageantes] pour [...] / [10] titres de [...] pour [...] / des balises de titre et de description méta / un audit / [3] domaines clés d'amélioration pour [...] / une liste de [10] mots-clés / un [bref] rapport [de suivi/de progrès/sur ...] / un calendrier [de contenu/de formation/de publication] / un post / programme [de formation] / procédure / un système de notation / un processus pour / une méthode pour [...] / une activité pratique [pour enseigner le concept de ...] / un scénario du quotidien [pour illustrer le concept] / des exercices pratiques [pour renforcer la compréhension] / des activités [pratiques/spécifiques] / des études de cas / des méthodes d'évaluation [pour mesurer ...] / des exemples [de questions/de tâches de [...] comme ...] / un examen [complet pour ...] / des études de cas / des projets de groupe / des débats / un test oral / un scénario de conversation / des critères d'évaluation [précis comme ...] / un webinaire [interactif sur ...] / une liste [d'outils/de suggestions/de mots-clés] / des cas d'utilisation / des démonstrations en direct / des astuces [peu connues pour ...] / une présentation [pour... sur .../approfondie sur ...] / un atelier dynamique sur [...] / des discussions de groupe / des ressources / comment [utiliser/implémenter] / le code [JavaScript en Python] / les différences [de syntaxe et de structure entre les deux langages] / les avantages [à/de/en termes de...] / les meilleures pratiques / pour détecter des vulnérabilités / des modifications [pour améliorer la lisibilité et .../pour optimiser .../pour le rendre plus .../afin qu'il soit en conformité avec ...] / un mécanisme / un article [de blog/de nouvelles de 500 mots] / une étude de cas [sur la manière dont ...] / un livre blanc [sur ...] / une métadescription / [5] exemples de titres [optimisés pour ...] / [3] objectifs [principaux pour... et explique comment ces objectifs soutiennent la mission de ...] / le profil de [l'utilisateur idéal] / des KPI [pour mesurer ...] / [5] sources externes [de contenu] / [3] idées [de publication] / des explications [pour leur succès] / un échéancier / les principaux livrables / les ressources nécessaires [pour la mise en place de ...] / les écarts entre [...] et [...] / une communication [expliquant.../adressée à ... pour ...] / un compte rendu [de fin de projet]

**contrainte/affinement** : pour chaque idée, fournis / prends en compte [les facteurs/des aspects tels que ...] / inclus [une variété de [...]/des mesures-clés/une stratégie de ciblage/des idées/des recommandations/des suggestions/des conseils sur/ des informations sur/des éléments tels que ...] / utilise les données [...] pour guider [ton estimation] / chaque [persona] devra comprendre des détails comme [...] / présente les différentes options, leurs avantages et inconvénients et propose une stratégie / identifie [les concurrents, leurs points forts et faibles et donne des recommandations sur comment se différencier/les goulots d'étranglement] / propose des solutions / pour chaque [prospect], inclus des informations pertinentes comme [... et la raison pour laquelle ...] / assure-toi d'inclure [des considérations pour.../des mots-clés pertinents/des questions sur/des tutoriels étape par étape/des astuces pour .../des conseils/des exemples concrets de ...]  / identifie [les points faibles [...] et propose des améliorations pour [...] / ces [messages] devraient être [personnalisés, engageants et [...] / identifie les opportunités pour améliorer [...] / explique chaque [...] et comment [elle] pourrait être appliquée dans le contexte de [...] / le [...] devrait [remercier [...], rappeler [...] et ...] / identifie les lacunes, propose des améliorations [basées sur ces données]  et rédige un plan d'action détaillé pour l'amélioration [ce plan doit comprendre ...] / ce [...] devrait inclure [...] / identifie les tendances, les défis, les opportunités et donne des recommandations / assure-toi d'aborder la situation [avec soin, d'apporter une solution et de rétablir la confiance ...] / qui aborde [les principaux aspects de ...] / assure-toi que [l'enquête soit concise, ciblée et conçue pour ...] / le [...] doit comprendre [...] / assure-toi d'exprimer [notre intérêt tout en laissant la porte ouverte à ...] / les [...] devraient explorer [...] / assure-toi [d'adresser les préoccupations du [...]/de lui donner des commentaires constructifs et de lui souhaiter bonne chance] / [...] qui couvre [...] / le [scénario] devrait refléter [...] / la [lettre] devrait reconnaitre ses [...] et souligner son [...] / le [questionnaire] devrait aborder des aspects tels que[...]/le ton doit être [...] et aider à [résoudre ...] / [...] incluant [des critères tels que/des mesures clés comme ...] et suggère [des améliorations basées sur ces données] / les [sujets] devront être [pertinents et intéressants] pour [...] / assure-toi de respecter les limites de caractères recommandés / inclus [une analyse de.../des suggestions d'amélioration pour chacun des [...]/les informations clés comme .../des détails sur .../comment tu envisages de ...] / explique pourquoi [ces mots-clés] seraient [efficaces] / veille à aligner le contenu sur [notre stratégie ...] / en fournissant [les détails de ...] et en indiquant [...] / tout en suggérant [des produits alternatifs] / en détaillant [les conditions ...] / tout en prenant en compte [ses demandes spécifiques] / en suggérant de [...] / en mettant l'accent sur [...] / en identifiant [les points forts et les domaines d'amélioration] / en utilisant des méthodes telles que [...] / assure-toi d'y intégrer [des informations sur ...] / propose des exemples concrets [d'outils ou de plateformes à utiliser ainsi que des activités interactives] / intègre [différents types de questions/des schémas/des exercices pratiques/des études de cas/des critères spécifiques tels que/une chronologie [...], des analyses de [...], des activités pratiques, des ressources comme ...] / en y intégrant [des techniques, des études de cas, des activités interactives, ...] / assure-toi d'y mentionner [...] / assure-toi d'y détailler [les problèmes [...], les étapes à suivre [...]] / en y fournissant des détails sur [...] / intègre [des conseils pratiques, des signes à surveiller, des ressources ...] / en conformité avec [les directives ...] / n'oublie pas d'inclure [les différentes étapes, des conseils et des bonnes pratiques] / les [...] peuvent inclure [des questions/des histoires pertinentes/des défis/des opportunités de partage/...] / qui met en valeur / et explique pourquoi ces [...] seraient pertinentes pour [...] / assure-toi de mettre en valeur [les caractéristiques ...] / assure-toi de remercier [le client] pour [...] / assure-toi d'aborder [ses préoccupations] et de souligner [comment l'entreprise ...] / assure-toi d'exprimer [l'engagement de l'entreprise ... et de détailler ...] / assure-toi d'expliquer [l'impact et le potentiel de chaque risque] / ton approche devrait viser à [...] / assure-toi d'évaluer [la probabilité et l'impact de chaque risque] / ta réponse devrait viser à [minimiser l'impact de [...] sur ...] / la demande implique [...] / utilise [des mesures comme ...] / le [plan] devrait préciser [...] / assure-toi de présenter [le problème, son impact potentiel et ta stratégie pour le gérer]


## Idées et exemples de prompts 

Cf. livres pour les exemples de prompts suivants :

1. entreprenariat
a. validation d'idées : génération d'idées, analyse SWOT, recherche de marché, estimation de la demande, création de persona
b. planification d'entreprise : rédaction d'un énoncé de mission, création d'un plan d'entreprise, analyse des risques, stratégie de croissance, rédaction d'un pitch, élaboration d'un plan de financement, rédaction d'un résumé exécutif, évaluation de l'entreprise, négociation avec les investisseurs, planification stratégique, analyse de la concurrence, planification financière, optimisation des opérations, gestion d'équipes
2. Ventes
a. prospection et acquisition de clients : recherche de prospects, stratégie de prospection, optimisation du taux de conversion, engagement de clients, analyse du parcours client
b. négociation et clôture de ventes : préparation à la négociation, scénario de clôture de vente, objection de vente, techniques de persuasion, suivi après une présentation de vente
c.  stratégie de vente : évaluation du processus de vente, développement de la stratégie de vente, optimisation de la proposition de valeur, planification des ventes, analyse de la performance des ventes
d. gestion de la relation client : gestion des plaintes, amélioration de l'expérience client, rétention des clients, analyse de la satisfaction des clients, étude de cas client
3. Ressources humaines
a. recrutement et embauche : création annonce emploi, rédaction courriel après entrevue, analyse CV, simulation questions d'entretien, rédaction lettre de projet
b. développement et formation du personnel : création plan de formation, feedback de performance, élaboration parcours de carrière, rédaction d'un courrier de formation, élaboration guide d'intégration
c. gestion des performances : analyse, retour
d. rédaction d'un plan d'amélioration de la performance : évaluation, rédaction d'un plan de formation
e. relations avec les employés et engagement : amélioration de l'engagement, gestion des conflits, rédaction lettre d'appréciation, création enquête de satisfaction, élaboration politique d'équité
4. Marketing
a. E-mail marketing : création plan de campagne, rédaction e-mail de bienvenue, élaboration e-mail de relance, analyse de performance des campagnes d'e-mail marketing
b. Content marketing : rédaction e-mail promotion spéciale, création de contenus de blog engageants, optimisation contenu pour SEO, rédaction légendes engageantes, création titres de blog attrayants, rédaction e-mails marketing convaincants
c. SEO et SEM : rédaction balises méta optimisées pour SEO, audit SEO d'un site web, création campagne SEM, recherche mots-clés pour nouveau contenu, analyse performance SEO
d. Réseaux sociaux : création calendrier de contenu pour réseaux sociaux, rédactions de posts de médias sociaux engageants, analyse des performances des médias sociaux, gestion des commentaires et interactions sur les réseaux sociaux, planification d'une campagne de publicité sur les réseaux sociaux
5. Service client
a. Gestion des réclamations : traitement des retours de produits, gestion des remboursements, réponse à une réclamation, gestion des échanges de produits, traitement de plaintes
b. réponse aux demandes des clients : réponse à une question, gestion d'une demande de suivi de commande, réponse à une demande d'informations, gestion d'une demande de réservation, réponse à une demande d'assistance technique
c. formation des employés du service client : création d'un programme de formation, évaluation des compétences, formation continue, gestion des retours, intégration nouvelles technologies
d. mesure de la satisfaction client : création d'un questionnaire de satisfaction, analyse des retours clients, mise en place système de notation, évaluation des retours après réclamation, mesure fidélité
6. Enseignement et formation
a. Préparation d'un cours : planification, intégration multimédia, activité sur la probabilité, intégration pensée critique, cours précis
b. Evaluation des élèves : évaluation compétences, examen, évaluation pensée critique, test oral, évaluation du développement socio-émotionnel
c. Formation continue pour enseignants : programme sur les méthodologies d'enseignement, webinaire sur les outils numériques, présentation sur la gestion de la classe, guide sur la pédagogie différenciée, atelier sur l'apprentissage collaboratif
d. Communication avec les parents : lettre e bienvenue pour nouvelle année, courriel sur une sorite, rapport de progrès, courriel sur les candidatures universitaires, lettre sur bien-être mental
7. Développement web
a. Langages de programmation : exploration avancée de JavaScript, astuces CSS avancées, utilisations avancées de Python, optimisation de l'environnement et développement PHP, HTML5 et API
b. Traduction de code informatique : de JavaScript à Python, de PHP à Node.js, de Python à Java, de JavaScript à TypeScript, de Python à Rust
c. Conception et UX : critique de l'UX, conception interface utilisateur réactive, intégration UX dans processus de développement, accessibilité web, création prototype
d. Sécurité web et conformité : audit de sécurité, conformité RGPD, traitement données sensibles, contrôles d'accès, prévention attaques XSS
8. Rédacteurs web
a. Création de contenu : rédaction article de blog, création étude de cas, écriture guide, rédaction livre blanc, création article de nouvelles
b. SEO : optimisation mots-clés, rédaction métadescriptions, création titres SEO-friendly, optimisation contenu existant, balisage contenu SEO
c. Rédaction de scripts : de podcast, de vidéo YouTube, publicitaire, de webinaire, de vidéo explicative
d. Révision et édition : édition article de blog, correction erreurs grammaires et style, amélioration lisibilité, révision d'un script de podcast, édition SEO
9. Community management
a. Stratégie de CM : rédaction d'un plan CM, établissement des objectifs, définition communauté cible, élaboration stratégie d'engagement, évaluation de la performance
b. Création et curation de contenu : élaboration calendrier de contenu, curation contenu, création contenu engageant, publication promotion, publication réponse
c. Gestion des médias sociaux : élaboration stratégie médias sociaux, création calendrier de publication, analyse performance médias sociaux, élaboration campagne médias sociaux, gestion commentaires et réactions
d. Gestion de crise : élaboration plan gestion de crise, communication de crise, analyse de crise, communication interne en temps de crise, reprise après crise
10. Gestion de projets
a. Planification de projet : définition objectifs, création échéancier, identification ressources, création plan, établissement des livrables
b. Gestion des risques du projet : identification des risques, élaboration plan de contingence, gestion des problèmes, analyse des risques, planification de la réponse aux risques
c. Suivi et contrôle du projet : suivi avancement, analyse des écarts, gestion des modifications, évaluation qualité, contrôle des coûts
11. Communication de projet : création d'un plan de communication, communication des changements, communication des risques, présentation des progrès, compte rendu final



{% include links.html %}
