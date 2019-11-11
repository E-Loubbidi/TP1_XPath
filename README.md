# TP 1 **: XPath**

![XPath](XPath.png)

---

Ce TP concerne des requetes XPath éxécutées sur le fichier [mondial.xml](https://www.dbis.informatik.uni-goettingen.de/Mondial/mondial.xml).

---

1. Quel est la population de l'afrique ?

```XPath

sum(/mondial/country/population[last()][following-sibling::encompassed[@continent="africa"]])

```
2. Combien de pays a-t-on en Afrique ?

```XPath

count(/mondial/country/encompassed[@continent="africa"]/..)

```

3. Quel sont les pays traversés par le Amazone ?

```XPath

/mondial/country/province/city/located_at[@river="river-Amazonas"]/../../../name

```

4. Quel sont les pays qui bordent l'ocean atlantique ?

```XPath

/mondial/country/province/city/located_at[@sea="sea-Atlantic"]/../../../name

```

5. Combien de Musulmans en Europe ?

```XPath

sum(/mondial/country/religion[text()="Muslim"][preceding-sibling::encompassed[@continent="europe"]]/(@percentage * ../population[last()])) div 100

```

6. Combien et quel sont les pays qui sont à plus d'un continent ?

```XPath

count(/mondial/country[count(encompassed/@continent)>1]/name)

/mondial/country[count(encompassed/@continent)>1]/name

```

7. Quel sont les pays limitrophes de l'Allemagne ?

```XPath

/mondial/country/name[text()="Germany"]/following-sibling::border

```

8. Quel est le pays ou la population est la plus dense ?

```XPath

/*/country[population[last()] = max(/*/country/population[last()])]

```
