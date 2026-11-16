# Conception de la solution

Remplacez les indications entre crochets par les informations connues. Si un choix reste à faire, indiquez-le.

## 1. Résultats attendus

*But : préciser les livrables du projet, leur format et leur utilité.*

| Résultat ou livrable | Description et format | Objectif auquel il répond |
| --- | --- | --- |
| [Nom du résultat] | [Description, format ou « à préciser »] | [Objectif concerné] |

## 2. Flux de traitement

*But : décrire les principales étapes, des données d’entrée aux résultats.*

Vous pouvez aussi ajouter un schéma Mermaid pour illustrer le flux de traitement.

| Étape | Données d’entrée | Traitement prévu | Résultat |
| --- | --- | --- | --- |
| Vérifier et sélectionner les scènes | Scènes Landsat candidates couvrant Sherbrooke durant l’été 2024 | Vérifier le produit, les dates, l’emprise, les métadonnées, le CRS, la résolution, la couverture nuageuse et les conditions d’accès | Scènes retenues et caractéristiques consignées dans l’analyse des données |
| Préparer les données d’imagerie | Scènes retenues et limite administrative de Sherbrooke à identifier | Définir les bandes nécessaires après vérification du produit, puis préparer les données à l’emprise de travail | Données préparées; paramètres à documenter |
| Identifier et caractériser les zones vertes | Données préparées et définition des zones vertes à confirmer | Méthode d’identification et indicateurs à choisir après l’évaluation des données | Carte, couche d’attributs et tableau de synthèse envisagés; formats à préciser |

## 3. Tests et vérifications

*But : prévoir comment vérifier que les traitements fonctionnent et que les résultats sont cohérents.*

| Élément à vérifier | Vérification prévue | Résultat attendu |
| --- | --- | --- |
| Scènes Landsat retenues | Comparer dates, emprise, métadonnées, résolution, couverture nuageuse et conditions d’accès | Scènes couvrant le territoire et la période d’étude, avec les caractéristiques et limites documentées |
| CRS et unités | Lire les métadonnées et comparer avec celles des autres couches retenues avant tout calcul de superficie | Références et unités connues et compatibles avec les mesures prévues |
| Zones et superficies produites | Examiner la couverture, les seuils et les résultats cartographiques une fois la méthode définie | Résultats cohérents avec la définition des zones vertes et les limites de résolution documentées |
