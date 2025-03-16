---
title: Python snippets
tags: [Python, programming]
last_updated: March 16, 2025
keywords: Python, programming
summary: "codes Python fréquemment utilisés"
sidebar: mydoc_sidebar
permalink: Python_snippets.html
folder: mydoc
---

{% include note.html content="Davantage de snippets sure git.vs.ch" %}


[article de blog](https://www.stat4decision.com/fr/introduction-a-polars-une-alternative-rapide-a-pandas/) sur **polars** comme alternative à **pandas**


### Method chaining et pandas

*[source](https://www.stat4decision.com/fr/method-chaining-avec-la-librairie-pandas/)*

Modifier des colonnes avec *assign*

Création ou modification d’une colonne « longueur » en lui attribuant la valeur 0 :

```{Python}
df.assign(longueur=0)
```

Modification des colonnes « name » et « gender » :

```{Python}
df.assign(name=lambda df_: df_.name.str.title(),
          gender=lambda df_: df_.gender.map({1: "M", 2: "F"}))
```

Sélection selon condition

Par exemple, sélection des lignes où l’année de vaut pas « XXXX » :

```{Python}
df.query('year != "XXXX"')
```

ou bien avec une lambda :

```{Python}
df.loc[lambda df_: df_.year != "XXXX"]
```


L'application d’une fonction quelconque à des Series ou à des DataFrames peut s’effectuer avec la méthode pipe(func, *args, **kwargs).

Par exemple, la division des valeurs des colonnes d’un DataFrame par leur moyenne respective :

```{Python}
df.pipe(lambda df_: df_.div(df_.mean()))
```

Exemple avec plotly :

```{Python}
import pandas as pd
import matplotlib.pyplot as plt

with plt.style.context('seaborn'):
    (pd
     .read_csv('data/nat2021_csv.zip',sep=';', na_values="", keep_default_na=False)
     .rename(columns={'sexe': 'gender', 'preusuel': 'name', 'annais': 'year', 'nombre': 'births'})
     .query('(name != "_PRENOM_RARES") and (year != "XXXX")')
     .astype({'year': int})
     .assign(name=lambda df_: df_.name.str.title(),
             gender=lambda df_: df_.gender.map({1: "M", 2: "F"}))
     .loc[:, ['year', 'name', 'gender', 'births']]
     .sort_values(['year', 'gender', 'births', 'name'], ascending=[True, True, False, True])
     .reset_index(drop=True)
     .pivot_table(index="year", columns="gender", values="births", aggfunc="sum")
     .plot
     .line(title="Nombre de naissances par année et par genre")
    )
```

Exemple avec plotly.express :

```{Python}
import pandas as pd
import plotly.express as px

(pd
 .read_csv('data/nat2021_csv.zip',sep=';', na_values="", keep_default_na=False)
 .rename(columns={'sexe': 'gender', 'preusuel': 'name', 'annais': 'year', 'nombre': 'births'})
 .query('(name != "_PRENOM_RARES") and (year != "XXXX")')
 .astype({'year': int})
 .assign(name=lambda df_: df_.name.str.title(),
         gender=lambda df_: df_.gender.map({1: "M", 2: "F"}))
 .loc[:, ['year', 'name', 'gender', 'births']]
 .sort_values(['year', 'gender', 'births', 'name'], ascending=[True, True, False, True])
 .reset_index(drop=True)
 .pivot_table(index="year", columns="gender", values="births", aggfunc="sum")
 .pipe(px.line, title="Nombre de naissances par année et par genre", width=800, labels={"value":""})
)
```


### Opérateur morse

*[source](https://www.stat4decision.com/fr/operateur-morse-python-3-8/)* 

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


### Début et fin de script

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
