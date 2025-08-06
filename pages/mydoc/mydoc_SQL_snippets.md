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

### Recherche floue avec SOUNDEX pour retrouver un nom similaire

<!-- Bouton Copier -->
<button class="copy-btn" data-clipboard-target="#codeBlock1">Copier</button>
<pre><code id="codeBlock1">
SELECT *
            FROM V_EXPLOITATIONS
            WHERE SOUNDEX(Nom1) = SOUNDEX('Clement') 
            AND 
            [Année données annuelles]=2025
</code></pre>

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

### Inline If (IIF)

<button class="copy-btn" data-clipboard-target="#codeBlock5">Copier</button>
<pre><code id="codeBlock5">
</code></pre>

### Essai de conversion pour détecter des erreurs de format

<button class="copy-btn" data-clipboard-target="#codeBlock6">Copier</button>
<pre><code id="codeBlock6">
    SELECT [No CT exploitation], [Code forme exploitation]
  FROM dbo.V_EXPLOITATIONS
WHERE [Année données annuelles]=2025 AND
TRY_CAST([No CT exploitation] AS INT) IS NULL
AND [No CT exploitation] IS NOT NULL;
</code></pre>

<button class="copy-btn" data-clipboard-target="#codeBlock7">Copier</button>
<pre><code id="codeBlock7">
</code></pre>

<button class="copy-btn" data-clipboard-target="#codeBlock8">Copier</button>
<pre><code id="codeBlock8">
</code></pre>

<button class="copy-btn" data-clipboard-target="#codeBlock9">Copier</button>
<pre><code id="codeBlock9">
</code></pre>

<button class="copy-btn" data-clipboard-target="#codeBlock10">Copier</button>
<pre><code id="codeBlock10">
</code></pre>

<button class="copy-btn" data-clipboard-target="#codeBlock11">Copier</button>
<pre><code id="codeBlock11">
</code></pre>

<button class="copy-btn" data-clipboard-target="#codeBlock12">Copier</button>
<pre><code id="codeBlock12">
</code></pre>

<button class="copy-btn" data-clipboard-target="#codeBlock13">Copier</button>
<pre><code id="codeBlock13">
</code></pre>

<button class="copy-btn" data-clipboard-target="#codeBlock14">Copier</button>
<pre><code id="codeBlock14">
</code></pre>

<button class="copy-btn" data-clipboard-target="#codeBlock15">Copier</button>
<pre><code id="codeBlock15">
</code></pre>




{% include links.html %}
