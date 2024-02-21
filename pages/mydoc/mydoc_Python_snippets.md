---
title: Python snippets
tags: [Python, programming]
last_updated: February 21, 2024
keywords: Python, programming
summary: "codes Python fréquemment utilisés"
sidebar: mydoc_sidebar
permalink: Python_snippets.html
folder: mydoc
---

{% include note.html content="Ne sont pas disponibles en lignes, usage offline uniquement" %}



##### Début et fin de script

```{Python}


from datetime import datetime
now = datetime.now()
start = now.strftime("%d/%m/%Y %H:%M:%S")

print("> Start " + start)

#[...]

now = datetime.now()
end = now.strftime("%d/%m/%Y %H:%M:%S")

print("start :\t" + start)
print("end:\t" + end)
print("*** DONE")

```



{% include links.html %}
