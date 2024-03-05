---
title: R snippets
tags: [R, programming]
last_updated: February 21, 2024
keywords: R, programming
summary: "codes R fréquemment utilisés"
sidebar: mydoc_sidebar
permalink: R_snippets.html
folder: mydoc
---

{% include note.html content="Ne sont pas disponibles en lignes, usage offline uniquement" %}

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

##### Début et fin de script
<!-- Bouton Copier -->
<button class="copy-btn" data-clipboard-target="#codeBlock1">Copier</button>

<pre><code id="codeBlock1">

rm(list=ls())
require(openxlsx)
require(readxl)

setwd("//infra.vs.ch/dfs/SCA-DLW/PDIRECTS/1_Marie/...")

startTime <- Sys.Date()

# [...]

cat(paste0("**** done\n"))
cat(paste0("start : ", startTime, "\n"))
cat(paste0("end : ", Sys.Date(), "\n"))

</code></pre>




{% include links.html %}
