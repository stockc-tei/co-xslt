[![Build Status](https://travis-ci.org/conditor-project/co-xslt.svg?branch=master)](https://travis-ci.org/conditor-project/co-xslt)
# co-xslt

## Présentation

Le module `co-xslt` est un module de la chaine de traitement Conditor permettant de transformer un fichier XML et de lui appliquer une transformation XSL. Ce module se base sur le dépot `conditor-project/tei-conditor` pour lui fournir les fichiers XSL pour les différentes transformations XSL afin d'avoir une sortie en TEI.

## Configuration

Le fichier de configuration du canevas permet d'assigner une valeur à une variable présente dans une feuille de style.

Exemple :

Mettre la valeur "2020/10/10" à la variable "DateAcqu" lors de l'ingestion. 

Ajouter cette balise dans la feuille de style (le fichier XLST) :

```xml
<xsl:param name="DateAcqu"/>
```

Éditer le fichier de configuration du canevas (businessParams.json) :

```sh
$ nano load/co-xslt/businessParams.json
```

Ajouter les données suivantes :

```json
{
  "DateAcqu": "2020/10/10"
}
```

## Fonctionnement

### Structure d'entrée

Les champs requis dans le JSON d'entrée sont les suivants :

```json
{
  "originDocPath": "test/dataset/pubmed/pubmed-11748933.xml",
}
```

### Structure de sortie

Un champ `teiDocPath` est créé contenant le chemin du chemin vers le fichier xml TEI.

```json
{
  "originDocPath": "test/dataset/pubmed/pubmed-11748933.xml",
  "teiDocPath": "/home/rmeja/Dev/conditor/co-xslt/test/dataset/pubmed/pubmed-11748933.tei"
}
```
