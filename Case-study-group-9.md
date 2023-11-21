---
title: "\"Cas d'étude : <nom du groupe>\""
description: '"Etude de cas DevOps sur LibreOffice"'
"date:": 2023-11-10
authors: "[François BECHET, Thibaut BERG, Maxime DE RYCKE]"
tags: []
---
# Introduction

Dans le cadre du cours [[INFOM126] Automated Software Engineering](https://directory.unamur.be/teaching/courses/INFOM126/2023) donné par DEVROEY Xavier et assisté par MAQUOI Jérôme ,
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

À propos du déploiement, The Document Foundation a opté pour la mise en place de [release plans](https://wiki.documentfoundation.org/ReleasePlan), c’est à dire qu’ils essaient de publier une nouvelle version à date fixe (le vendredi), mais ils se laissent une marge d'erreur de quelques jours au cas où ils rencontreraient des problèmes techniques, de build ou tout autre type de problème qui nécessiterait quelques modifications.
Ce release plan fixe, pour chaque version, les semaines de déploiement des fixes et améliorations ([schéma](https://wiki.documentfoundation.org/ReleasePlan#Version_scheme): alpha, beta, RC, ...).

Pour la release initiale d’une nouvelle version ils sortent une version alpha et ensuite une version beta.

LibreOffice sort deux versions major par an en même temps que les sorties de Gnome et d’autres logiciels open sources important pour marquer deux grands évènements par an.

LibreOffice sort une bugfix release chaque mois après la sortie de la version major.

Ils ont deux branches principales :

- Une branche Fresh: leur release la plus récente

- Une branche Still: la release précédente pour les utilisateurs plus sensibles comme les entreprises

Le déploiement à date fixe force les contributeurs à avoir une certaine discipline dans leur gestion de la modification du code, ce qui a pour effet de garder un bon rythme de déploiement malgré le côté Open Source qui implique parfois un manque de moyens.

Cependant cela demande une certaine automatisation du build process, ce qui est déjà prévu dans leur [plan d'accélération](https://wiki.documentfoundation.org/ReleasePlan#Accelerating_the_release_cycle).

### Mean time to restore (MTTR)

Signalement des bugs via deux plateformes :

- [Bugzilla](https://bugs.documentfoundation.org/):  permet d’ouvrir un rapport de bugs, permet de classer les bugs en donnant un nom/tag, de trouver des bugs dupliquer

- [Redmine](https://redmine.documentfoundation.org/projects?jump=welcome): même chose mais pour les sites web et les services web de LibreOffice

L'utilisation de Bugzilla et de Redmine permet de réduire le temps entre la détection d'une erreur et son patch grâce à une centralisation de la plateforme de gestion des bugs qui permet une meilleure collaboration entre les contributeurs.

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
- "Membership Committee" ou MC: gère les demandes d'adhésion et les renouvellements des membres et organiser les élections du BoD.
- "Board of trustees" (les membres): toute personne contribuant activement aux projets de la fondation, répondant à [certains critères](https://www.documentfoundation.org/media/statutes.pdf) et ayant rempli un [formulaire d'adhésion](https://membership.documentfoundation.org/).

D'autres entités aident le BoD, sans être des organes formels de la fondation:

- "Engineering steering Committee": composé des meilleurs développeurs de la communauté, cette entité offre une aide technique.
- "Advisory Board": forum pour les organisations pour fournir un soutien financier ou autre.

### Continuous delivery

Pour le continuous devlivery, The Document Foundation utilise [Jenkins](https://jenkins.libreoffice.org) afin d'automatiser les builds, les tests et les déploiements des différentes applications.
On peut voir sur leur Jenkins que des [builds journaliers](https://dev-builds.libreoffice.rg/daily/) sont lancés pour leurs applications.
Lancer des builds régulièrement permet de tester le code plus souvent et ainsi pouvoir identifier au plus tôt les différents problèmes présents.

Ils ont recourt à [TinderBox](https://ci.libreoffice.org/view/tb%20platform%20status) qui est leur outil d'aide à l'intégration continue. Ce dernier vérifie si le code de chaque projet compile sans erreurs et si la suite des tests est passée avec succès.
Un système de couleur permet de voir rapidement quels builds ont échoué ou réussi.
Sur le TinderBox de LibreOffice, lorsqu'un build échoue, on retrouve également le nom des personnes qui ont commit depuis le dernier build réussi.
Il s'agit d'un outil très visuel qui aide à déterminer quel projet nécessite une attention particulière afin de résoudre les différents bugs.

Un système de **nightly builds** permet d'offrire une version de libreOffice qui est encore en développement. Les nightly builds sont utilisé uniquement à des fins de tests et The Document Foundation ne fournit aucune garrantie sur ces versions.
Les développeurs ont également mis en place un système de **pre-release** afin de rendre disponible des versions "semblables" à la version finale mais la déconseillent pour un usage en production.

### Westrums Organizational Culture

[The Document Foundation](https://www.documentfoundation.org/) est une entité auto gouverné sous le principe de méritocratie, c’est à dire que les gens sont récompensés sur base de leurs efforts, qui met le fun en avant.

LibreOffice a été fondé avec la conviction que la culture qui émerge d’une fondation indépendante stimule le meilleur chez ses contributeurs ce qui amène aussi à produire un logiciel de meilleure qualité pour les utilisateurs.

Donc clairement LibreOffice est dans une culture générative avec une forte coopération de par son principe open source qui partage aussi les risques entre les collaborateurs.

### Identity

LibreOffice incarne les principes du logiciel libre. Basé sur [les quatre libertés fondamentales](https://fr.libreoffice.org/about-us/who-are-we/), le projet promeut la liberté d'exécution, de copie, de distribution, d'étude, de modification et d'amélioration du logiciel.

En favorisant l'accès gratuit aux outils de productivité bureautique, LibreOffice lutte contre la fracture numérique, encourage la préservation des langues maternelles, et s'oppose aux logiciels propriétaires.

Une attention particulière est apportée à la [diversité](https://wiki.documentfoundation.org/Diversity) des membres au sein de la fondation.

LibreOffice protège les droits des développeurs en utilisant des licences qui protège l’open source comme la [license GNU](https://github.com/LibreOffice/core/blob/master/COPYING).

Donc c’est une communauté guidée par l'engagement envers la qualité, la fiabilité, la sécurité et la flexibilité des Logiciels Libres qui offre des opportunités de contribution variées conformément aux idées de The Document Foundation.

## Description du pipeline de développement

Décrivez ici le pipeline de développement suivi par votre case study. Si vous ne trouvez pas assez d'informations sur ce qui est effectivement suivi, proposez-en un en fonction des informations rassemblées sur votre case study.

## Propositions d'améliorations

- Augmentation de la fréquence des releases

Pour l'instant, The Document Foundation publie une nouvelle version officielle majeure tous les 6 mois.
Il serait peut-être plus judicieux de diminuer le temps entre 2 releases afin de diminuer les potentiels problèmes accumulés durant cette longue période.

- Passer du système de release à "semaine fixe" vers un système de release quand la suite LibreOffice contient assez de nouveautés pour en faire une nouvelle version

Changer de "mode" de release permettrait d'éviter de faire des releases sans réel contenu mais également éviter la pression sur les developpeurs qui se dépêchent de finir leur modifications avant la date limite.

# Conclusion

# Other links

- <https://www.documentfoundation.org/certification-qna/>
- <https://fr.libreoffice.org/community/get-involved/>
