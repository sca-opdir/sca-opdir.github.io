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

{% include note.html content="Davantage de snippets disponibles sur git.vs.ch" %}


créer packages :
[https://tinyheero.github.io/jekyll/update/2015/07/26/making-your-first-R-package.html](https://tinyheero.github.io/jekyll/update/2015/07/26/making-your-first-R-package.html)


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

### Début et fin de script
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

### Charger ou installer les packages (début de ui.R)
<button class="copy-btn" data-clipboard-target="#codeBlock2">Copier</button>
<pre><code id="codeBlock2">
inst_pckg <- function(x, r='http://cran.us.r-project.org'){
  install.packages(x, repos=r)
}
all_pckgs <- c("shiny","DT","XML", "shinyjs", "openxlsx")
for(pck in all_pckgs){
  if(!require(pck, character.only = TRUE)){
    cat("will install package : ", pck,"\n")
    inst_pckg(pck)
  }  
}
</code></pre>

### Reshape
##### long
<button class="copy-btn" data-clipboard-target="#codeBlock3">Copier</button>
<pre><code id="codeBlock3">
l_dt <- reshape(w_dt, 
        varying = list(keepcols), # Spécifier les colonnes à pivoter
        v.names = "Value", # Nom de la colonne pour les valeurs pivotées
        idvar = c(id_col, an_col), # Colonnes identifiant chaque observation,
        times = keepcols, ## pour éviter que variable soit 1,2,3,etc.
        timevar = "Variable", # Nom de la nouvelle colonne pour les noms des variables pivotées
        direction = "long") # Spécifier la direction du pivot
</code></pre>

##### wide
<button class="copy-btn" data-clipboard-target="#codeBlock4">Copier</button>
<pre><code id="codeBlock4">
w_dt <- reshape(l_dt[,c(id_col, an_col, "VariableA", "Diff")],
                 direction="wide",
                 timevar = "VariableA",
                 idvar = c(id_col, an_col))
</code></pre>

                 

{% include links.html %}
