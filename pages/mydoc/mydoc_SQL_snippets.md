---
title: SQL snippets
tags: [SQL, programming]
last_updated: August 06, 2025
keywords: SQL, programming
summary: "exemples de requêtes SQL"
sidebar: mydoc_sidebar
permalink: SQL_snippets.html
folder: mydoc
---

<script src="https://cdnjs.cloudflare.com/ajax/libs/clipboard.js/2.0.8/clipboard.min.js"></script>
<script>
var clipboard = new ClipboardJS('.copy-btn');
clipboard.on('success', function(e) {
    console.info('Texte copié :', e.text);
    e.clearSelection();
});
clipboard.on('error', function(e) {
    console.error('Erreur lors de la copie :', e);
});
</script>


### Tri ascendant 

<button class="copy-btn" data-clipboard-target="#codeBlock2">Copier</button>
<pre><code id="codeBlock2">
SELECT DISTINCT Nom1
      FROM V_EXPLOITATIONS
            WHERE
            [Année données annuelles]=2025
              ORDER BY Nom1 AS
</code></pre>

### Nombre d'exploitations par année 

! attention : pas vraiment correct car le Témoin suppression n'est pas annualisé !

<button class="copy-btn" data-clipboard-target="#codeBlock3">Copier</button>
<pre><code id="codeBlock3">
SELECT   [Année données annuelles], 
  COUNT(DISTINCT [No CT exploitation]) AS nb_exploitations_distinctes
  FROM dbo.V_EXPLOITATIONS
WHERE [Code forme exploitation] IN (1, 2, 6) AND
[Témoin suppression exploitation] IS NULL
  GROUP BY [Année données annuelles]
  ORDER BY [Année données annuelles] ASC;
</code></pre>


### Inline If (IIF)

<button class="copy-btn" data-clipboard-target="#codeBlock4">Copier</button>
<pre><code id="codeBlock4">
SELECT 
  [No CT exploitation],
  IIF([Acompte bloqué] = 'Oui', 'Blocage', 'OK') AS StatutAcompte
FROM V_EXPLOITATIONS WHERE
            [Année données annuelles]=2025;
</code></pre>

### Conversion du niveau de qualité (LTRIM, COALESCE)

<button class="copy-btn" data-clipboard-target="#codeBlock5">Copier</button>
<pre><code id="codeBlock5">
SELECT  DISTINCT TOP 10
 [Id de la surface], [Niveau SPB],  
 LTRIM(REPLACE(COALESCE([Niveau SPB], '0'), 'Niveau de qualité', '')) AS NiveauNum
FROM V_SURFACES
WHERE [Exercice comptable]=2025
</code></pre>

Ici on aurait aussi pu utiliser ISNULL : 
* ISNULL(expr, valeur_par_defaut) est spécifique à SQL Server et ne prend que 2 arguments.
* COALESCE(expr1, expr2, ..., exprN) est standard SQL, peut prendre plusieurs arguments, et retourne la première non NULL.


### Essai de conversion pour détecter des erreurs de format

<button class="copy-btn" data-clipboard-target="#codeBlock6">Copier</button>
<pre><code id="codeBlock6">
    SELECT [No CT exploitation], [Code forme exploitation]
  FROM dbo.V_EXPLOITATIONS
WHERE [Année données annuelles]=2025 AND
TRY_CAST([No CT exploitation] AS INT) IS NULL
AND [No CT exploitation] IS NOT NULL;
</code></pre>

### Garder la partie gauche avant un délimitateur

<button class="copy-btn" data-clipboard-target="#codeBlock7">Copier</button>
<pre><code id="codeBlock7">
SELECT DISTINCT 
    [No CT exploitation],
    LEFT([No CT exploitation], CHARINDEX('/', [No CT exploitation]) - 1) AS NomDecoupe
    FROM V_EXPLOITATIONS
    WHERE [Année données annuelles] = 2025
    AND [Code forme exploitation] IN (20)
    AND CHARINDEX('/', [No CT exploitation]) > 0
    </code></pre>

### Obtenir différents niveaux d'agrégation dans une seule requête (regroupement conditionnel avec GROUPING SETS)

<button class="copy-btn" data-clipboard-target="#codeBlock8">Copier</button>
<pre><code id="codeBlock8">
    SELECT 
[Commune OFS Secteur], 
[Exercice comptable], 
SUM([Surface exploitée]) AS TotalSurface
FROM V_SURFACES
WHERE [Exercice comptable] = 2025
GROUP BY GROUPING SETS (
  ([Commune OFS Secteur], [Exercice comptable]),
  ([Commune OFS Secteur]),
  ([Exercice comptable]),
  ()
)
</code></pre>


### Recherche sur plusieurs colonnes avec COALESCE

Attention : n'est pas équivalent à un OR. Par ex. ci-dessous, teste LIKE sur la 1ère valeur non-nulle Nom4, Nom3, etc. dans cet ordre ; ne passe pas à la colonne suivante dès que non-nul trouvé

<button class="copy-btn" data-clipboard-target="#codeBlock9">Copier</button>
<pre><code id="codeBlock9">
  SELECT DISTINCT [No CT exploitation], Nom1, Nom2, Nom3, Nom4
  FROM V_EXPLOITATIONS
      WHERE COALESCE(Nom4, Nom3, Nom2, Nom1) LIKE '%Studer%' AND
    [Année données annuelles]=2025
</code></pre>

### Classement des exploitations par leur surface exploitée (RANK)

<button class="copy-btn" data-clipboard-target="#codeBlock10">Copier</button>
<pre><code id="codeBlock10">
SELECT TOP 5
    [No CT exploitation],
    SUM([Surface exploitée]) AS TotalSurface,
    RANK() OVER (ORDER BY SUM([Surface exploitée]) DESC) AS Rang
    FROM V_SURFACES
    WHERE [Exercice comptable]=2025 AND
    [Code forme exploitation] IN (1,2,6) AND
    [Code culture surface] NOT LIKE '09%'
    GROUP BY [No CT exploitation]
    ORDER BY Rang;
</code></pre>

### Recherche floue avec SOUNDEX pour retrouver un nom similaire

<button class="copy-btn" data-clipboard-target="#codeBlock1">Copier</button>
<pre><code id="codeBlock1">
SELECT *
            FROM V_EXPLOITATIONS
            WHERE SOUNDEX(Nom1) = SOUNDEX('Clement') 
            AND 
            [Année données annuelles]=2025
</code></pre>

 ### Filtrage par similarité de texte avec DIFFERENCE() (phonétique avancée)

Permet des requêtes plus tolérantes que SOUNDEX. Score entre 0 (mots pas du tout similaires) et 4 (les deux mots sonnent très similaires)

<button class="copy-btn" data-clipboard-target="#codeBlock11">Copier</button>
SELECT DISTINCT Nom1 
  FROM V_EXPLOITATIONS
    WHERE DIFFERENCE(Nom1, 'Zufferey') >= 3;
<pre><code id="codeBlock11">
</code></pre>



### Pivot statique

Le pivot statique demande que tu connaisses à l’avance les colonnes cibles (ex. années).

<button class="copy-btn" data-clipboard-target="#codeBlock14">Copier</button>
<pre><code id="codeBlock14">
    SELECT 
    [No exploitation],
    ISNULL([A], 0) AS A,
    ISNULL([B], 0) AS B,
    ISNULL([D], 0) AS D
FROM (
    SELECT 
        [No exploitation],
        [code catégorie],
        SUM([Total UGB]) AS TotalUGBSomme
    FROM V_ANIMAUX
    WHERE 
        [Exercice comptable] = 2025
        AND [Catégorie déclaration animaux] = 'Nombre au jour de référence (têtes)'
    GROUP BY 
        [No exploitation], 
        [code catégorie]
) AS SourceTable
PIVOT (
    SUM(TotalUGBSomme)
    FOR [code catégorie] IN ([A], [B], [D])
) AS PivotTable
ORDER BY [No exploitation];

</code></pre>

### Pivot dynamique

Le pivot dynamique construit cette liste automatiquement (pratique si la liste change souvent).
<button class="copy-btn" data-clipboard-target="#codeBlock15">Copier</button>
<pre><code id="codeBlock15">
DECLARE @cols NVARCHAR(MAX), @colsIsNull NVARCHAR(MAX), @query NVARCHAR(MAX);

-- 1. Liste des colonnes entre crochets (pour le pivot)
SELECT @cols = STRING_AGG(QUOTENAME([code catégorie]), ',')
FROM (
    SELECT DISTINCT [code catégorie]
    FROM V_ANIMAUX
    WHERE [Exercice comptable] = 2025
      AND [Catégorie déclaration animaux] = 'Nombre au jour de référence (têtes)'
) AS tmp;

-- 2. Liste des colonnes enveloppées dans ISNULL (pour la sélection finale)
SELECT @colsIsNull = STRING_AGG('ISNULL(' + QUOTENAME([code catégorie]) + ', 0) AS ' + QUOTENAME([code catégorie]), ', ')
FROM (
    SELECT DISTINCT [code catégorie]
    FROM V_ANIMAUX
    WHERE [Exercice comptable] = 2025
      AND [Catégorie déclaration animaux] = 'Nombre au jour de référence (têtes)'
) AS tmp;

-- 3. Construire la requête dynamique complète
SET @query = N'
SELECT [No exploitation], ' + @colsIsNull + '
FROM (
    SELECT 
        [No exploitation], 
        [code catégorie], 
        SUM([Total UGB]) AS TotalUGBSomme
    FROM V_ANIMAUX
    WHERE [Exercice comptable] = 2025
      AND [Catégorie déclaration animaux] = ''Nombre au jour de référence (têtes)''
    GROUP BY [No exploitation], [code catégorie]
) AS src
PIVOT (
    SUM(TotalUGBSomme)
    FOR [code catégorie] IN (' + @cols + ')
) AS pvt
ORDER BY [No exploitation];';

-- 4. Exécuter la requête dynamique
EXEC sp_executesql @query;

</code></pre>


 ### Compactage/conversion en JSON, XML, etc. 

##### JSON

<button class="copy-btn" data-clipboard-target="#codeBlock12">Copier</button>
<pre><code id="codeBlock12">
    SELECT TOP 10 Nom1, Commune, [Année données annuelles]
FROM V_EXPLOITATIONS
FOR JSON AUTO;
</code></pre>

##### XML

<button class="copy-btn" data-clipboard-target="#codeBlock13">Copier</button>
<pre><code id="codeBlock13">
    SELECT TOP 10 Nom1, Commune, [Année données annuelles]
FROM V_EXPLOITATIONS
FOR XML AUTO, ELEMENTS;
</code></pre>

(ELEMENTS force les colonnes à apparaître comme des éléments XML (tags) au lieu d’attributs)

### Autres fonctions

##### STRING_SPLIT

(garde toutes les parties, renvoie le résultat sur plusieurs lignes)

<code>
CROSS APPLY STRING_SPLIT([No CT exploitation], '/')
</code>

{% include links.html %}
