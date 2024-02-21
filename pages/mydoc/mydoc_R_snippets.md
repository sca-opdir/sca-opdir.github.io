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



##### Début et fin de script

```{R}
rm(list=ls())
require(openxlsx)
require(readxl)

setwd("//infra.vs.ch/dfs/SCA-DLW/PDIRECTS/1_Marie/...")

startTime <- Sys.Date()

# [...]

cat(paste0("**** done\n"))
cat(paste0("start : ", startTime, "\n"))
cat(paste0("end : ", Sys.Date(), "\n"))

```



{% include links.html %}
