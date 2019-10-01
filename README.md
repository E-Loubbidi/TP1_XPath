# TP 1 **: XPath**

![XPath](XPath.png)

---

Ce TP concerne des requetes XPath éxécutées sur le fichier [mondial.xml](https://www.dbis.informatik.uni-goettingen.de/Mondial/mondial.xml).

---

1. Quel est la population de l'afrique

```XPath

sum(/*/country/population[/*/country/encompassed[@continent = "africa"]])

```
2. Combien de pays a-t-on en Afrique

```XPath

count(/*/country[encompassed[@continent = "africa"]])

```

3. Quel sont les pays traversés par le Amazone

```XPath

/*/river[name[contains(.,"Amazonas")]]

```

4. Quel sont les pays qui bordent l'ocean atlantique

```XPath

/*/sea/name[contains(.,"Atlantic Ocean")]

```

5. Combien de Musulmans en Europe

```XPath

count(/*/country[religion[contains(.,"Muslim")] and encompassed[@continent = "europe"]])

```

6. Combien et quel sont les pays qui sont à plus d'un continent

```XPath

count(/*/country[count(encompassed[@continent])>1])

/*/country[count(encompassed[@continent])>1]

```

7. Quel sont les pays limitrophes de l'Allemagne

```XPath

/*/country[border[@country="D"]]

```

8. Quel est le pays ou la population est la plus dense

```XPath

/*/country[population[last()] = max(/*/country/population[last()])]

```