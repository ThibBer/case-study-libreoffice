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
- Un tableur : [Calc](https://libreoffice.org/discover/calc)
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
En ce qui concerne les moyens mis en place pour améliorer le temps entre la demande et la satisfaction de celle-ci, nous pouvons d'abord mentionner l'aspect open-source. En effet, LibreOffice dispose de plusieurs [repositories Github](https://github.com/LibreOffice). Certains repositories contiennent des Github Actions, mais celles-ci semblent très peu utilisées. 

Ces repositories Github sont des repositories "read only", car le projet LibreOffice dispose également de [son propre Git](https://git.libreoffice.org/core/). Ceci permet donc à n'importe qui de jeter un oeil sur le code pour éventuellement y contribuer en ajoutant des fonctionnalités ou améliorant le code existant. 

Ensuite, The Document Foundation met à disposition [une plateforme Bugzilla](https://bugs.documentfoundation.org/) pour signaler les bugs sur les différents outils inclus dans LibreOffice. Cela permet aux contributeurs de pouvoir s'y retrouver dans les différents bugs et de les corriger plus rapidement lorsqu'ils ont été signalés. Leur plateforme Bugzilla comprend une documentation, expliquant comment l'utiliser.

### Deployment frequency
À propos du déploiement, The Document Foundation a opté pour la mise en place de [release plans](https://wiki.documentfoundation.org/ReleasePlan).
Ce release plan fixe, pour chaque version, les semaines de déploiement des fixes et amélioration (alpha, beta, RC, ...).

### Mean time to restore (MTTR)

### Change fail percentage
Afin de réduire le taux d'erreurs, The Document Foundation met en place plusieurs pratiques assez classiques.

Tout d'abord, toute demande de modification de code passe par une étape de revue de code via [leur plateforme Gerrit](https://gerrit.libreoffice.org), au travers d'une pull request.

Ensuite, le projet LibreOffice sollicite également des contributeurs afin de réaliser [plusieurs sortes de tests](https://wiki.documentfoundation.org/QA) (tests d'interface, tests de régression, ...).

## Enabling factors

### Lean management
Le projet LibreOffice évolue grâce à la collaboration de ses nombreux contributeurs. Le développement est mené par la communauté pour la communauté. Leur philosophie est décrite dans [leur manifeste](https://www.documentfoundation.org/media/tdf-manifesto.pdf).

Sur le site de LibreOffice, une page ["Community map"](https://www.libreoffice.org/community/community-map/) permet de voir où se situent certains contributeurs influents de LibreOffice, ayant interviewés, avec un moyen de les contacter.

En ce qui concerne la communication entre contributeurs, des mailing lists sont mises à disposition. Il est également possible de discuter avec les contributeurs via des [canaux de discussion IRC](https://wiki.documentfoundation.org/Website/IRC).

Plus globalement, The Document Foundation est gérée par [différentes fonctions](https://fr.libreoffice.org/about-us/governance/):
- "Board of directors" ou BoD: les administrateurs principaux des projets et des différentes équipes de The Document Foundation.
- "Membership Committee" ou MC: gérer les demandes d'adhésion et les renouvellements des membres et organiser les élections du BoD.
- "Board of trustees" (les membres): toute personne contribuant activement aux projets de la fondation, répondant à [certains critères](https://www.documentfoundation.org/media/statutes.pdf) et ayant rempli un [formulaire d'adhésion](https://membership.documentfoundation.org/).

### Continuous delivery

### Westrums Organizational Culture

### Identity

## Description du pipeline de développement
Décrivez ici le pipeline de développement suivi par votre case study. Si vous ne trouvez pas assez d'informations sur ce qui est effectivement suivi, proposez-en un en fonction des informations rassemblées sur votre case study.

## Propositions d'améliorations
- Augmentation de la fréquence des releases

# Conclusion
