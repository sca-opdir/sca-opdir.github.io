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

{% include note.html content="Davantage de snippets sure git.vs.ch" %}


[article de blog](https://www.stat4decision.com/fr/introduction-a-polars-une-alternative-rapide-a-pandas/) sur **polars** comme alternative à **pandas**


##### Opérateur morse

permet de simultanément faire une allocation et un test dans la même expression. 

pour gagner des lignes de code et des allocations

```{Python}
liste_init = ["Python","PEP","conda"]

liste_filtree = [x.upper() for x in liste_init if "P" in x.upper()] 
```

remplacé par 

```{Python}
liste_init = ["Python","PEP","conda"]

liste_filtree = [y for x in liste_init if "P" in (y:=x.upper())] 
```


```{Python}
fichier_python = open("python.txt")
# on fait une boucle sur les lignes jusqu'à
# trouver le mot python
line = fichier_python.readline()
while line:
    if "python" in line:
        print("On a trouvé python") 
        break
        
    line = fichier_python.readline()
```

remplacé par

```{Python}
fichier_python = open("python.txt")
# on fait une boucle sur les lignes jusqu'à
# trouver le mot python
while line := fichier_python.readline():
    if "python" in line:
        print("On a trouvé python") 
        break
```


```{Python}
import numpy as np

# on crée une matrice de nombres aléatoires
data = np.random.random(1000).reshape(100,10)
n_col = data.shape[1]

if n_col > 10 :
    print("Nombre de colonnes : {}".format(n_col))
elif n_col == 10 :
    print("On a bien 10 colonnes")
```


remplacé par

```{Python}
import numpy as np

# on crée une matrice de nombres aléatoires
data = np.random.random(1000).reshape(100,10)

if (n_col := data.shape[1]) > 10 :
    print("Nombre de colonnes : {}".format(n_col))
elif n_col == 10 :
    print("On a bien 10 colonnes")
```


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
