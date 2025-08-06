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


{% include links.html %}
