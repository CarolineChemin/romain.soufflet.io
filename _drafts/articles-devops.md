# Devops et SRE : De quoi s'agit-il ?

Dans le précédent article (lien ici) je parle de la production. Mais qu'est-ce
que ça a avoir avec les termes *DevOps* et *SRE* ? Je ne prétendrai pas de
pouvoir donner des définition claire et universelle pour ces mots mais je pense
pouvoir éclaircir les concepts sous-jacents.

Traditionnelement, dans l'environnement informatique, nous rencontrons le schéma
suivant:

* Une ou plusieurs équipe de développement
* Une équipe d'administrateur systèmes

Et cette organisation entraîne généralement des problèmes de communications.

Les développeurs veulent plus de contrôle sur l'environnement qui fait tourner
leur applications et tiennent souvent les administrateurs pour responsable de ce
manque de liberté.

Les administrateurs ont pour missions de garder la productions stable, garantir
la sécurité du système. Mais ils sont surtout impliqué dans les astreintes et se
réveiller à 2 heures du matin pour un disque dur plein, ça ne fait pas plaisir


## La culture DevOps

La culture DevOps se présente en premier lieu sur le plan organisationnel. Il
s'agit d'abolir les barrière entre les équipes de développement et les équipes
d'administrateurs.

En s'affranchissant de ces barrière, on permet aux développeur et administrateur
de communiquer. On obtient ainsi des développeur qui prennent conscience de ce
qu'est la production et comment on dois s'en occuper, mais aussi des
administrateurs capable de programmer et automatiser leurs maintenances.

La collaboration va aussi permettre de redéfinir comment l'application se
construit. On passe d'un model ou les developpeur propose un package avec un
documentation d'installation, a une collaboration à tout les niveau de
conception.

Les processus de livraison qui en découle ressemblent généralement à celui là:

* L'idée ou le besoin émis par le client avec la collaboration de profils
  techniques
* Le développement de cette fonctionnalité
* La revue de code et les tests automatisée
* Le tests fonctionnel, par le client directement
* Le déploiements en production

On parle donc de culture **DevOps** et **d'amélioration continue**. En effet,
lorsque vos équipes techniques se réunissent autour d'une table et prennent le
temps de regarder leurs propres manières de travailler, ils identifieront les
passages douloureux qui ont besoin d'être redéfinit.

C'est un éléments central dans l'implémentation de la culture **DevOps**, tout
le monde est **DevOps** et tout le monde travail dans l'intérêt de l'équipe.

## L'échec de la culture DevOps

* De l'idée à la production
* Une stabilité accrue
* Au détriment de la souplesse

## SRE: Site Reliability Engineer

L'ingénieur de fiabilité du site #faisTonCanadien est une notion qui nous viens
d'un livre publié par Google. Il s'agit d'une organisation qui permet de faire
mieux collaborer les équipes de développements et les équipes opérationnel.

L'idée principale part du constat suivant:

* Les développeurs ont pour mission de développer plus de nouvelles
  fonctionnalités et livrer rapidement
* Les équipes qui déploit ont pour objectif de garantir la stabilité de leur
  applications

On a donc deux rôles distinct ayant chacune des objectifs en contradiction. Cela
entraîne des tenssions, et c'est pour ces raisons qu'on oppose très souvent les
« devs » et les « ops ».

* On parle donc de SLI, SLO, et SLA
* Que veut dire "disponnible"
* Qu'est-ce qui est acceptable ?

et concrétement:

* L'environnement de tests QA
* La preproduction
* La production

Ici, on concentre notre énergie à la stabilité de la production. Les compétences
sont purement "Ops", mais nous avons besoin de la développer.

* Infra as Code
* Disaster recovery
* Achitecture immutable
* Industrialisation

Beaucoup d'entreprise se retrouve avec des équipes SRE, isoler des équipes de
développement.

## Être créatifs

* D'autre environnements, à la volé
* Des mises à jours plus fréquente

## Conclusion

========================================


### Les développeur

Tout projets informatiques a besoin de développeur à la base. Les logiciels
sont tous issues de code source, écrit par des humains : Les développeur.

Ce code source est compliqué, plus facile à écrire qu'a lire. Et comme il a
été écrit par un humain, il comporte des erreurs. On peut facilement identifier
plusieurs familles d'erreurs.

* Des erreurs de syntaxe, de compilation : le logiciel ne fonctionne juste pas
* Des bugs, un comportement innatendu par le développeur
* Des erreurs fonctionnel, un traitement qui ne correspond pas à ce que le
  client souhaite
* Des fonctionnalité en trop, ou manquante.

```
* Des tests
 * Unitaire / Fonctionel, en fait je m'en fou
 * Qu'ils soient indépendant
* Une documentation
 * Pourquoi on écris une documentation
 * Quels type de documentation
```

### L'intégration
 * Environnement neutre
 * Collecte des logs
 * La livraison
### Le déploiement
 * Le maintiens en conditions opérationnel
 * Le fail recovery
### La culture devops
 * L'Onboarding, Facilité l'arrivé de nouveau membre
 * Savoir que faire quand quelqu'un part
 * Le monitoring
 * La sécurité

## Continuous Whatever (2/4) : Continuous Integration

### Ça veut dire quoi ?
 * L'intégration
 * Automatiquement ? Really ?

### OK, mais pourquoi ?
 * Parce que si on fait économiser du temps, on peut développer plus de chose
 * L'environnement est neutre
 * On repart toujours "from scratch" donc la mise en prod posera moins de problème

### Comment je met ça en place moi ?
 * Différentes étapes pour bootstrapper le travail
 * Instaurer la culture "continous truc" dans l'équipe

## Continuous Whatever (3/4) : Continuous Delivery

### Plus loin que l'intégration
 * Relire la partie sur l'intégration
 * Intégration et Déploiement sont deux choses distincte
 * Note sur les downtime => BlueGreen

### Les validations
 * On va valider avant de déployer
 * Les données de tests
 * Les accés à la production

### Le résultat
 * Le temps de mise en prod
 * Le taux d'erreurs
 * Dire non aux devs et aux clients

## Continuous Whatever (4/4) : Pipeline de production

### Continuous Integration + Continuous Delivery
 * From code to Production

### Les validations : Version 2
 * Tout n'est pas automatisable