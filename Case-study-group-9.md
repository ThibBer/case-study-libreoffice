---
title: "\"Cas d'étude : <nom du groupe>\""
description: '"Etude de cas DevOps sur LibreOffice"'
"date:": 2023-11-10
authors: "[François BECHET, Thibaut BERG, Maxime DE RYCKE]"
tags: []
---
# Introduction
Dans le cadre du cours [[INFOM126] Automated Software Engineering](https://directory.unamur.be/teaching/courses/INFOM126/2023), 
nous avons réalisé un case-study sur [LibreOffice](https://www.libreoffice.org) afin de répertorier différentes métriques liées au DevOps.

LibreOffice a été créé en septembre 2010 [The Document Foundation](https://www.documentfoundation.org/).
Elle continue d'ailleurs à maintenanir et améliorer les produits à l'heure actuelle.

# Description du cas d'étude
## Contexte et domaine d'application

## Description générale des fonctionnalités offertes
LibreOffice est une suite logicielle libre et open source.
Elle comporte plusieurs applications :
- Un éditeur de documents : [Writer](https://libreoffice.org/discover/writer)
- Un tableau : [Calc](https://libreoffice.org/discover/calc)
- Un créateur de présentations : [Impress](https://libreoffice.org/discover/impress)
- Un éditeur de documents graphiques (diagrammes et organigrammes) : [Draw](https://libreoffice.org/discover/draw)
- Un gestionnaire de base de données : [Base](https://libreoffice.org/discover/base)
- Un éditeur de formules et d'équations : [Math](https://libreoffice.org/discover/math)
- Un module de création de diagrammes : [Diagrammes](https://libreoffice.org/discover/charts)

# Analyse DevOps du cas d'étude

## Identification des facteurs mis en place favorisant le DevOps
Pour chaque métrique DORA, identifier les éléments mis en place (gestion de projet, pipeline de développement, outils, pratiques de développement, ...) permettant de favoriser la métrique en question.

Pour chaque facteur favorisant les performances organisationnelles et non-commerciales identifié par Forsgren et al., identifier si ce facteur est présent ou non et comment celui-ci est mis en place.

### Lead time
En ce qui concerne les moyens mis en place pour améliorer le temps entre la demande et la satisfaction de celle-ci, nous pouvons d'abord mentionner l'aspect open-source. En effet, LibreOffice dispose de plusieurs [repositories Github](https://github.com/LibreOffice). Ceci permet donc à n'importe qui de jeter un oeil sur le code pour éventuellement y contribuer. Certains repositories contiennent des Github Actions, mais celles-ci semblent très peu utilisées.

Ensuite, The Document Foundation met à disposition [une plateforme Bugzilla](https://bugs.documentfoundation.org/) pour signaler les bugs sur les différents outils inclus dans LibreOffice. Cela permet aux contributeurs de pouvoir s'y retrouver dans les différents bugs et de les corriger plus rapidement lorsqu'ils ont été signalés. Leur plateforme Bugzilla comprend une documentation, expliquant comment l'utiliser.

### Deployment frequency
À propos du déploiement, The Document Foundation a opté pour la mise en place de [release plans](https://wiki.documentfoundation.org/ReleasePlan).
Ce release plan fixe, pour chaque version, les semaines de déploiement des fixes et amélioration (alpha, beta, RC, ...).


## Description du pipeline de développement
Décrivez ici le pipeline de développement suivi par votre case study. Si vous ne trouvez pas assez d'informations sur ce qui est effectivement suivi, proposez-en un en fonction des informations rassemblées sur votre case study.

## Propositions d'améliorations
Propositions d'éléments techniques ou organisationnels à ajouter permettant de favoriser le DevOps

# Conclusion