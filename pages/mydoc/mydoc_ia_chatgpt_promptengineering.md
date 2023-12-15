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
* Conférence InnoVibes de S. Lendi
* [*6 stratégies d'openAI pour obtenir de meilleurs résultats*](https://platform.openai.com/docs/guides/prompt-engineering)
* [*7 conseils Zdnet*](https://www.zdnet.com/article/7-advanced-chatgpt-prompt-writing-tips-you-need-to-know)
* *<https://www.promptingguide.ai>
* 
## Eléments-clés du prompt

* contexte
* rôle
* cheminement à suivre
* cadrage et contraintes

## Méthode ACTIF-VE (M. Corthésy)

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

## Méthode PROMPT

1. **Paysage** : plantez le décor, décrivez le contexte, la toile de fond, soit le paysage de votre commande
2. **Rôle** : placez ChatGPT dans un rôle spécifique
3. **Objectif** : procurez l'objectif attendu de votre commande
4. **Moyen(s)** : donnez des indices, des exemples ou autres moyens à ChatGPT pour accomplir l'objectif
5. **Particularité(s)** : évoquez les autres particularités et/ou contraintes dont ChatGPT doit tenir compte
6. **Ton** : spécifiez le ton de la réponse attendue (formel, humoristique, décontracté, etc.)

Pas obligatoire d'avoir toujours les 6, mais 1-3 quasi-obligatoires.

Exemple :

*[P] Nous sommes dans le domaine culinaire. [R] Durant toute notre conversation, tu es un chef cuisinier très expérimenté. [O] Le but est de procurer des conseils pratiques à des débutants qui savent juste cuire des pâtes. [M] Les instructions seront fournies dans l'ordre chronologique, [P] mais sans ajouter de numérotation avant chaque tâche. Les recettes seront utilisées pour un blog, elles ont un maximum de mille mots. [T] Tu t'exprimes sur un ton jovial, inspirant et avec bienveillance. Montre que tu as compris en m'expliquant comment faire une omelette.*


## Rebondir sur la réponse de ChatGPT (message de suivi)

* Une fois la réponse obtenue, relancer avec une autre question
* Ex. : faire faire un tableau avec les caractéristiques principales des concurrents puis follow-up message "tu es un commercial expert [...] ; sur la base des informations récoltées dans le tableau sur les concurrents, trouve les faiblesses de chaque concurrent ... utilise ton analyse pour établir une stratégie ... "

## Amélioration continue du prompt

* Passer dans un mode itératif et améliorer continuellement le prompt selon les besoins spécifiques 
* ChatGPT révise le prompt à chaque étape
* Attention à la limitation de la mémoire (rappeler les éléments clés de la discussion si besoin)

## Faire poser des questions pour optimiser la réponse

"[P] On prépare une offre Black Friday. [R] Tu es expert en copywriting, tu as la plum de David Ogilvy. [O] On veut optimiser la conversion sur cette offre, avec la meilleure proposition de valeur. Propose-moi une offre et un argumentaire. **Mais avant, pose-moi des questions pour optimiser ta réponse.**"


## Transfomer chatGPT en expert de notre entreprise 

Dans un instant je vais te demander de rédiger du contenu efficace pour mon entreprise. Il s'agit du contenu d'un site, d'un blog, de publications pour Instagram et d'e-mails de vente. **Avant de commencer j'aimerais que tu comprennes parfaitement mon entreprise et mes clients. Pose-moi au moins 20 questions sur mon entreprise, mes clients, mon audience et tout ce dont tu as besoin pour réaliser la tâche au mieux possible.**


## Retrouver le prompt afin de reproduire du contenu existant

Par exemple : si on trouve une description de produit très bien faite, et on veut adopter le même style pour ses propres produits.

*Etape 1* <br>
USER : "Rétroconcevoir signifie créer un prompt à partir d'un texte. Tu es un expert en ingénierie de prompt, capable de rétr-concevoir des prompts sur la abse d'n texteou d'une information. Este-ce que tu peux me donner un exemple d'un prompte rétro-conçu ?"
ChatGPT : [...]

*Etape 2* <br>
USER : "Bien, maintenant, génère un modèle technique de ce prompt rétro-conçu."
ChatGPT : [...]

*Etape 3* <br>
USER : Rétro-conçoit un prompt pour ce texte : <insérer texte>. Assure-toi de prendre en compte le ton, le langage, la syntaxe, l'esprit et le style du texte, pour que ton prompte génère ce même texte.
ChatGPT : [...]

*Etape 4* <br>
USER : Je désire vendre <description du produit>. <Insérer le prompt créé par ChatGPT en [3]>.
ChatGPT : [...]


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

1. **Entreprenariat** <br>
a. <u>Validation d'idées</u> : génération d'idées, analyse SWOT, recherche de marché, estimation de la demande, création de persona<br>
b. <u>Planification d'entreprise</u> : rédaction d'un énoncé de mission, création d'un plan d'entreprise, analyse des risques, stratégie de croissance, rédaction d'un pitch, élaboration d'un plan de financement, rédaction d'un résumé exécutif, évaluation de l'entreprise, négociation avec les investisseurs, planification stratégique, analyse de la concurrence, planification financière, optimisation des opérations, gestion d'équipes

2. **Ventes** <br>
  a. <u>Prospection et acquisition de clients</u> : recherche de prospects, stratégie de prospection, optimisation du taux de conversion, engagement de clients, analyse du parcours client<br>
  b. <u>Négociation et clôture de ventes</u> : préparation à la négociation, scénario de clôture de vente, objection de vente, techniques de persuasion, suivi après une présentation de vente<br>
  c. <u>Stratégie de vente</u> : évaluation du processus de vente, développement de la stratégie de vente, optimisation de la proposition de valeur, planification des ventes, analyse de la performance des ventes<br>
  d. <u>Gestion de la relation client</u> : gestion des plaintes, amélioration de l'expérience client, rétention des clients, analyse de la satisfaction des clients, étude de cas client

3. **Ressources humaines** <br>
  a. <u>Recrutement et embauche</u> : création annonce emploi, rédaction courriel après entrevue, analyse CV, simulation questions d'entretien, rédaction lettre de projet<br>
  b. <u>Développement et formation du personnel</u> : création plan de formation, feedback de performance, élaboration parcours de carrière, rédaction d'un courrier de formation, élaboration guide d'intégration<br>
  c. <u>Gestion des performances</u> : analyse, retour<br>
  d. <u>Rédaction d'un plan d'amélioration de la performance</u> : évaluation, rédaction d'un plan de formation<br>
  e. <u>Relations avec les employés et engagement</u> : amélioration de l'engagement, gestion des conflits, rédaction lettre d'appréciation, création enquête de satisfaction, élaboration politique d'équité

4. **Marketing** <br>
  a. <u>E-mail marketing</u> : création plan de campagne, rédaction e-mail de bienvenue, élaboration e-mail de relance, analyse de performance des campagnes d'e-mail marketing<br>
  b. <u>Content marketing</u> : rédaction e-mail promotion spéciale, création de contenus de blog engageants, optimisation contenu pour SEO, rédaction légendes engageantes, création titres de blog attrayants, rédaction e-mails marketing convaincants<br>
  c. <u>SEO et SEM</u> : rédaction balises méta optimisées pour SEO, audit SEO d'un site web, création campagne SEM, recherche mots-clés pour nouveau contenu, analyse performance SEO<br>
  d. <u>Réseaux sociaux</u> : création calendrier de contenu pour réseaux sociaux, rédactions de posts de médias sociaux engageants, analyse des performances des médias sociaux, gestion des commentaires et interactions sur les réseaux sociaux, planification d'une campagne de publicité sur les réseaux sociaux

5. **Service client** <br>
  a. <u>Gestion des réclamations</u> : traitement des retours de produits, gestion des remboursements, réponse à une réclamation, gestion des échanges de produits, traitement de plaintes<br>
  b. <u>Réponse aux demandes des clients</u> : réponse à une question, gestion d'une demande de suivi de commande, réponse à une demande d'informations, gestion d'une demande de réservation, réponse à une demande d'assistance technique<br>
  c. <u>Formation des employés du service client</u> : création d'un programme de formation, évaluation des compétences, formation continue, gestion des retours, intégration nouvelles technologies<br>
  d. <u>Mesure de la satisfaction client</u> : création d'un questionnaire de satisfaction, analyse des retours clients, mise en place système de notation, évaluation des retours après réclamation, mesure fidélité

6. **Enseignement et formation** <br>
  a. <u>Préparation d'un cours</u> : planification, intégration multimédia, activité sur la probabilité, intégration pensée critique, cours précis<br>
  b. <u>Evaluation des élèves</u> : évaluation compétences, examen, évaluation pensée critique, test oral, évaluation du développement socio-émotionnel<br>
  c. <u>Formation continue pour enseignants</u> : programme sur les méthodologies d'enseignement, webinaire sur les outils numériques, présentation sur la gestion de la classe, guide sur la pédagogie différenciée, atelier sur l'apprentissage collaboratif<br>
  d. <u>Communication avec les parents</u> : lettre e bienvenue pour nouvelle année, courriel sur une sorite, rapport de progrès, courriel sur les candidatures universitaires, lettre sur bien-être mental

7. **Développement web** <br>
  a. <u>Langages de programmation</u> : exploration avancée de JavaScript, astuces CSS avancées, utilisations avancées de Python, optimisation de l'environnement et développement PHP, HTML5 et API<br>
  b. <u>Traduction de code informatique</u> : de JavaScript à Python, de PHP à Node.js, de Python à Java, de JavaScript à TypeScript, de Python à Rust<br>
  c. <u>Conception et UX</u> : critique de l'UX, conception interface utilisateur réactive, intégration UX dans processus de développement, accessibilité web, création prototype<br>
  d. <u>Sécurité web et conformité</u> : audit de sécurité, conformité RGPD, traitement données sensibles, contrôles d'accès, prévention attaques XSS

8. **Rédacteurs web** <br>
  a. <u>Création de contenu</u> : rédaction article de blog, création étude de cas, écriture guide, rédaction livre blanc, création article de nouvelles
  b. <u>SEO</u> : optimisation mots-clés, rédaction métadescriptions, création titres SEO-friendly, optimisation contenu existant, balisage contenu SEO
  c. <u>Rédaction de scripts</u> : de podcast, de vidéo YouTube, publicitaire, de webinaire, de vidéo explicative
  d. <u>Révision et édition</u> : édition article de blog, correction erreurs grammaires et style, amélioration lisibilité, révision d'un script de podcast, édition SEO

9. **Community management** <br>
  a. <u>Stratégie de CM</u> : rédaction d'un plan CM, établissement des objectifs, définition communauté cible, élaboration stratégie d'engagement, évaluation de la performance<br>
  b. <u>Création et curation de contenu</u> : élaboration calendrier de contenu, curation contenu, création contenu engageant, publication promotion, publication réponse<br>
  c. <u>Gestion des médias sociaux</u> : élaboration stratégie médias sociaux, création calendrier de publication, analyse performance médias sociaux, élaboration campagne médias sociaux, gestion commentaires et réactions<br>
  d. <u>Gestion de crise</u> : élaboration plan gestion de crise, communication de crise, analyse de crise, communication interne en temps de crise, reprise après crise

11. **Gestion de projets** <br>
  a. <u>Planification de projet</u> : définition objectifs, création échéancier, identification ressources, création plan, établissement des livrables<br>
  b. <u>Gestion des risques du projet</u> : identification des risques, élaboration plan de contingence, gestion des problèmes, analyse des risques, planification de la réponse aux risques<br>
  c. <u>Suivi et contrôle du projet</u> : suivi avancement, analyse des écarts, gestion des modifications, évaluation qualité, contrôle des coûts

12. **Communication de projet** : création d'un plan de communication, communication des changements, communication des risques, présentation des progrès, compte rendu final

## 6 stratégies openAI

1. **Instructions claires** <br>

a.	<u>ajouter des détails à la requête</u> <br>

b.	<u>faire adopter un persona au modèle</u><br>
"Message système" accessible aux utilisateurs de l’API peut être utilisé pour spécifier le persona utilisé par le modèle dans ses réponses. Exemple:<br>
*SYSTÈME : "Lorsque je vous demande de m'aider à écrire quelque chose, vous me répondez par un document qui contient au moins une blague ou un commentaire amusant dans chaque paragraphe."*<br>
*UTILISATEUR : "J'écris une note de remerciement à mon fournisseur de boulons en acier pour avoir livré à temps et dans un délai très court. Cela nous a permis de livrer une commande importante."*

c.	<u>utiliser des délimiteurs</u> (guillemets triples, balises XML, titres de section, etc.) pour délimiter les sections de l'entrée à traiter différemment<br>

d.	<u>préciser les étapes nécessaires à l'accomplissement d'une tâche</u><br>
  
Décomposer la tâche en **séquence d'étapes** <br>
*SYSTÈME : "Utilisez les instructions suivantes, étape par étape, pour répondre aux demandes de l'utilisateur."* <br>
*Étape 1 - L'utilisateur vous fournira un texte entre trois guillemets. Résumez ce texte en une phrase avec un préfixe indiquant "Résumé : ".*<br>
*Étape 2 - Traduisez le résumé de l'étape 1 en espagnol, avec un préfixe indiquant "Traduction : ".*<br>
*UTILISATEUR : """insérer le texte ici"""*


e.	<u>fournir des exemples</u> (ex: un exemple de style particulier difficile à décrire explicitement - *"few-shot" prompting*)<br>

f.	<u>préciser la longueur souhaitée (en nombre de mots, de phrases, de paragraphes, de puces, etc.)</u><br>
<b>Attention</b> : spécifier un nombre de mots ne permet pas d'obtenir une grande précision (plus fiable de demander des résultats avec un nombre spécifique de paragraphes ou de puces)


2. **Fournir un texte de référence** <br>
   
a.	<u>faire répondre le modèle à l'aide d'un texte de référence</u> (à partir des informations fournies dans le prompt - mais longueur limitée ! - ou en utilisant les *embeddings*)<br>

*SYSTÈME : "Utiliser les articles fournis, délimités par des triples guillemets, pour répondre aux questions. Si la réponse ne se trouve pas dans les articles, écrire "Je n'ai pas trouvé de réponse"."* <br>
*UTILISATEUR : <insérer les articles, chacun délimité par des guillemets triples>* <br>
*Question : <insérer la question ici>* <br>


b.	<u>faire répondre le modèle à l'aide de citations tirées d'un texte de référence</u><br>

*SYSTÈME : "Vous recevrez un document délimité par des guillemets triples et une question. Votre tâche consiste à répondre à la question en utilisant uniquement le document fourni et à citer le(s) passage(s) du document utilisé(s) pour répondre à la question. Si le document ne contient pas les informations nécessaires pour répondre à la question, écrivez simplement : "Informations insuffisantes" : "Informations insuffisantes". Si une réponse à la question est fournie, elle doit être annotée d'une citation. Utilisez le format suivant pour citer les passages pertinents ({"citation" : ...})."* <br>
*UTILISATEUR : <br>
"""<insérer le document ici>"" <br>
Question : <insérer la question ici>*


3. Diviser les tâches complexes en sous-tâches (flux de tâches plus simples, utiliser résultats des tâches antérieures pour construire les entrées des tâches ultérieures)<br>

a.	<u>classification des intentions</u> pour identifier les instructions les plus pertinentes :<br>
    - quand de nombreux ensembles d'instructions indépendants sont nécessaires pour traiter différents cas, <br>
    - commencer par classer le type de requête et utiliser cette classification pour déterminer quelles instructions sont nécessaires- commencer par classer le type de requête et utiliser cette classification pour déterminer quelles instructions sont nécessaires<br>
    - définir des catégories fixes et coder en dur les instructions pertinentes pour le traitement des tâches d'une catégorie donnée. <br>
    - commencer par classer le type de requête et utiliser cette classification pour déterminer quelles instructions sont nécessairesPeut être appliqué de manière récursive pour décomposer une tâche en une séquence d'étapes. <br>
    - chaque requête ne contient que les instructions nécessaires à l'exécution de l'étape suivante : réduction du taux d'erreur et éventuellement du coût<br>

Exemple : application de service à la clientèle où les requêtes peuvent être classées <br>
*SYSTÈME : Vous allez recevoir des demandes de service à la clientèle. Classez chaque requête dans une catégorie principale et une catégorie secondaire. Fournissez votre résultat au format json avec les clés : primaire et secondaire. <br>
Catégories primaires : Facturation, [...] <br>
Catégories secondaires de facturation : Désinscription ou mise à niveau, [...]<br>
Catégories secondaires du support technique : Dépannage, [...] <br>
Catégories secondaires de la gestion de compte : Réinitialisation du mot de passe, [...]<br>-
UTILISATEUR :  J'ai besoin de faire fonctionner mon internet à nouveau.*

b.	<u>résumer ou filtrer les dialogues précédents</u> (longueur de contexte limitée !)<br>
    - résumer les tours de parole précédents
    -	sélectionner dynamiquement les parties antérieures de la conversation qui sont les plus pertinentes pour la requête en cours (cf. recherche basée sur les *embeddings*)
    - pour résumer les longs documents : le faire par morceaux et construire un résumé complet de manière récursive (utiliser une séquence de requêtes pour résumer chaque section du document ; si nécessaire inclure un résumé courant du texte)

7. **Laisser le modèle "réfléchir" (demander une "chaîne de pensée")**<br>

a.	<u>faire élaborer au modèle sa propre solution</u> (ex: plutôt que demander si une réponse à un problème est correcte, demander de résoudre le problème et comparer la réponse obtenue) <br>

b.	<u>monologue intérieur ou séquence de questions</u> pour masquer le raisonnement du modèle (quand le raisonnement ne doit pas être visible pour l'utilisateur; demander une réponse dans un format structuré qui facilite leur analyse et seule une partie du résultat est rendue visible pour l'utilisateur)<br>

c.	<u>demander au modèle s'il a manqué quelque chose</u> lors des passages précédents (ex: dans l'analyse de longs documents, risque de s'arrêter trop tôt) : utiliser des requêtes de suivi (*follow-up*) pour trouver les extraits manqués lors des passages précédents<br>

*SYSTÈME : Vous disposez d'un document délimité par des guillemets triples. Votre tâche consiste à sélectionner les extraits qui se rapportent à la question suivante : "<insérer votre question ici>".<br>
Veillez à ce que les extraits contiennent tout le contexte nécessaire à leur interprétation - en d'autres termes, n'extrayez pas de petits bouts de texte auxquels il manque un contexte important. Fournissez des résultats au format JSON comme suit :<br>
[{"extrait" : "..."},<br>
...<br>
{"extrait" : "..."}]<br>
UTILISATEUR : """<insérer le document ici>"""<br>
ChatGPT : [...] <br>
UTILISATEUR : Existe-t-il d'autres extraits pertinents ? Veillez à ne pas répéter les extraits. Veillez également à ce que les extraits contiennent tout le contexte nécessaire à leur interprétation. En d'autres termes, n'extrayez pas de petits extraits auxquels il manque un contexte important.*<br>

9. **Utiliser des outils externes** <br>
    
a.	<u>recherche basée sur les embeddings</u><br>

*Embeddings de texte* = vecteurs permettant de mesurer la parenté entre les chaînes de texte ; utilisés pour mettre en œuvre une recherche de connaissances efficace. Découpage d'un texte en morceau, stockage des embeddings, puis lors d'une requête recherche vectorielle pour trouver les morceaux stockés les plus liés à la requête (c'est-à-dire les plus proches les uns des autres dans l'espace d'embedding). Permet ainsi d'ajouter des informations pertinentes à l'entrée du modèle de manière dynamique au moment de l'exécution.<br>

*Retrieval Augmented Generation (RAG)* = a technique that implements an information retrieval component to the generation process. Allowing us to retrieve relevant information and feed this information into the generation model as a secondary source of information.<br>

b.	<u>exécution de code (calculs, appels à API externes)</u> <br>

LLMs pas fiables pour calculs arithmétiques précis. Solution : demander d'écrire et d'exécuter du code au lieu d'effectuer ses propres calculs. Exemple :<br>
*SYSTÈME : Vous pouvez écrire et exécuter du code Python en l'entourant de triples crochets, par exemple ``code goes here``. Utilisez-le pour effectuer des calculs.<br>
UTILISATEUR : Trouvez toutes les racines réelles du polynôme suivant : 3*x**5 - 5*x**4 - 3*x**3 - 7*x - 10.* <br>

Appel à des API externes : expliquer à un modèle comment utiliser une API en lui fournissant de la documentation et/ou des exemples de code montrant comment utiliser l'API. Exemple :<br>
*SYSTÈME : Vous pouvez écrire et exécuter du code Python en l'entourant de triples crochets. Notez également que vous avez accès au module suivant pour aider les utilisateurs à envoyer des messages à leurs amis :
``python
import message
message.write(to="John", message="Hey, tu veux qu'on se retrouve après le travail ?")``*  

  c.	<u>donner accès à des fonctions spécifiques</u> (manière recommandée d'utiliser les modèles OpenAI pour appeler des fonctions externes)<br>

Via l'API "Chat Completions" : transmettre une liste de descriptions de fonctions dans les requêtes. Permet de générer des arguments de fonction selon les schémas fournis qui sont renvoyés par l'API au format JSON et peuvent être utilisés pour exécuter les appels de fonction. Les résultats de ces derniers sont ensuite réinjectés dans un modèle dans la requête suivante.<br>

11. Tester systématiquement les changements (mesurer les performances <u>globales</u> avec une suite de tests complète (*evals*))<br>
  a.	<u>évaluer les résultats du modèle</u> par rapport à des réponses de référence (ex: utiliser une requête de modèle pour compter combien de faits requis sont inclus dans la réponse)


 ## Divers

* TLDR (Too long; didn't read) : abréviation à utiliser dans le prompt pour obtenir un résumé ; exemple : <br>
 *TLDR https://www.agrarforschungschweiz.ch/fr/2023/12/combien-danimaux-de-rente-pour-une-utilisation-optimale-des-terres-en-suisse*
* demander à ChatGPT d'évaluer sa propre réponse

prompting sans exemple (zero-shot prompting), 

ne technique populaire et efficace pour le prompting est appelée prompting avec quelques exemples (few-shot prompting) où nous fournissons des exemples (c'est-à-dire des démonstrations)

Par exemple, vous pouvez effectuer une tâche simple de classification et fournir des exemples qui démontrent la tâche

Vous pouvez commencer par des messages simples et ajouter de plus en plus d'éléments et de contexte au fur et à mesure que vous cherchez à obtenir de meilleurs résultats

Il est également recommandé d'utiliser un séparateur clair comme "###" pour séparer l'instruction du contexte.

Il n'y a pas de tokens ou de mots-clés spécifiques qui conduisent à de meilleurs résultats. Il est plus important d'avoir un bon format et une prompt descriptive. En fait, fournir des exemples dans la prompt est très efficace pour obtenir les résultats souhaités dans des formats spécifiques

Un autre conseil courant lors de la conception de prompts est d'éviter de dire ce qu'il ne faut pas faire, mais de dire plutôt ce qu'il faut faire. Cela encourage une plus grande spécificité et met l'accent sur les détails qui conduisent à de bonnes réponses de la part du modèle.


le prompt "chain-of-thought" (CoT) permet des capacités de raisonnement complexes grâce à des étapes de raisonnement intermédiaires. Vous pouvez le combiner avec des prompts à quelques exemples pour obtenir de meilleurs résultats sur des tâches plus complexes qui nécessitent un raisonnement avant de répondre.
les auteurs affirment que c'est une capacité émergente qui se produit avec des modèles de langage suffisamment grands.
chain-of-thought-prompting.png

Une idée récente qui est sortie plus récemment est l'idée de zero-shot CoT (Kojima et al. 2022) qui consiste essentiellement à ajouter « Pensons étape par étape » aux prompt d'origine. 

zero-shot-cot-prompting.png

self-consistency
d'échantillonner plusieurs chemins de raisonnement divers à travers un CoT à quelques prises de vue et d'utiliser les générations pour sélectionner la réponse la plus cohérente. Cela permet d'améliorer les performances de l'incitation CoT sur les tâches impliquant un raisonnement arithmétique et de bon sens.

Generated Knowledge Prompting

capacité d'incorporer des connaissances ou des informations pour aider le modèle à faire des prédictions plus précises

Tree of Thoughts (ToT)
generalizes over chain-of-thought prompting and encourages exploration over thoughts that serve as intermediate steps for general problem solving with language models.

Retrieval Augmented Generation (RAG)

RAG takes an input and retrieves a set of relevant/supporting documents given a source (e.g., Wikipedia). The documents are concatenated as context with the original input prompt and fed to the text generator which produces the final output. This makes RAG adaptive for situations where facts could evolve over time. This is very useful as LLMs's parametric knowledge is static. RAG allows language models to bypass retraining, enabling access to the latest information for generating reliable outputs via retrieval-based generation.



{% include links.html %}
