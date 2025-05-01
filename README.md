# Vue d'ensemble 

## Contexte et vision
Dans le cadre de ce projet, vous serez amenés à réaliser une application web complète de gestion de stocks. Le commanditaire souhaite disposer d'une application moderne et professionnelle permettant de gérer l'inventaire de plusieurs boutiques. L'accent est mis sur la qualité du code, la sécurité et l'expérience utilisateur. Le projet doit également intégrer Github Actions pour l'intégration continue, préparant ainsi les étudiants aux exigences du monde professionnel.

## Objectifs pédagogiques
Approfondir la maîtrise de Django : modèles, vues génériques, templates, signaux et système d'authentification
Concevoir une architecture modulaire et évolutive : séparation par applications (catalogue, entrepôt, reporting, utilisateurs).
Mettre l'accent sur la sécurité et les bonnes pratiques Web (système d'authentification, permissions, CSRF, etc).
Introduire les fondements DevOps : tests d'intégration dans un pipeline GitHub Actions

# Fonctionnalités

## L'application web devra proposer les fonctionnalités suivantes :

  *1. Gestion des utilisateurs et rôles*
Inscription, authentification, réinitialisation de mot de passe.

  *2. Catalogue produits*
CRUD complet, import/export CSV.

  *3. Multi-entreprises / multi-sites*
Possibilité de rattacher des stocks à plusieurs sociétés, chaque utilisateur étant limité à son périmètre.

  *4. Mouvements de stock*
Entrées, sorties, historisation avec horodatage.

  *5. Alertes seuil critique*
Notification dans l'application lorsque la quantité passe sous le seuil défini.

  *6. Tableau de bord & statistiques*
Graphiques simples (quantités par catégorie, évolution mensuelle) rendus avec Chart.js.

  *7. Administration personnalisée*
Interface admin (affichage, filtres, recherche) permettant la gestion des utilisateurs, produits, stocks, etc.

* 3.1 Récit utilisateur principal
En tant que propriétaire de plusieurs entreprises, je veux pouvoir gérer les stocks de mes différents magasins depuis une seule interface, afin de suivre facilement les niveaux d'inventaire et d'être alerté quand les produits atteignent un seuil critique.



# Spécifications

## Spécifications techniques

### Architecture

Application Django classique avec base de données.

Langage : Python 3.11 minimum et Django 5.x.

Dépendances tierces conseillées : pytest-django, django import/export, django cleanup, django crispy forms, django-environ.


### Modèles
Product : SKU, nom, description, prix, seuil d'alerte
Location : nom, adresse, type (dépôt/boutique)
Stock : produit, lieu, quantité
Movement : produit, lieu source/destination, quantité, date, raison
Vues
Vue spéciale pour les mouvements avec formulaire dynamique.
Dashboard avec graphiques Chart.js.

### Tests

Tests unitaires.
Tests fonctionnels.
Fixtures pour données de test.
description

### Livrables attendus

#### Dépôt GitHub public contenant :
- Code source complet et commenté
- Jeux de données d'exemple (fixtures/initial_data.json)
- Scripts ou instructions de lancement
- Documentation utilisateur dans le README.md (installation, commandes, exemples)
  
#### Jeu de tests automatisés :
pytest exécutés par un workflow GitHub Actions.


# Planning

### Planification & jalons

| Période  | jalon  | Objectifs  |
| :--------------- |:---------------:| :-----|
| Semaine 1 | Initialisation | - Création du projet Django et configuration Git<br>- Installation des dépendances de base<br>- Configuration de la CI avec GitHub Actions |
| Semaines 2-3 | Modélisation | - Création des modèles (User, Product, Stock)<br> - Premières migrations et fixtures<br>- Configuration de l'admin Django basique |
| Semaines 4-5 | Fonctionnalités core | - Authentification et gestion des rôles<br> - CRUD produits avec interface web<br> - Premiers tests avec pytest-django |
| Semaines 6-7 | Fonctionnalités avancées | - Système de notifications et alertes<br> - Tableau de bord avec graphiques<br> - Import/export de données |
| Semaines 8 | Production ready | - Configuration Docker et déploiement<br> - Documentation technique et utilisateur<br> - Tests de sécurité et optimisations |



# gestion des risques

### ![warning](image.jpg "warning.jpg") Gestion des risques

| Risque | 	Mesure préventive |
| :--------------- | :-----|
| Complexité de la gestion multi-entreprises	| Commencer par un POC simple, valider l'architecture des modèles avec le mentor dès le début |
| Problèmes de performance BDD	| Optimiser les requêtes, utiliser select_related/prefetch_related |
| Difficultés avec Gitub Actions	| Partir de templates, commencer avec des tests basiques |

# Ressources annexes

### Annexes

[Documentation officielle Django](https://docs.djangoproject.com/en/5.2/)<br>
[Guide sécurité Django](https://docs.djangoproject.com/en/5.2/topics/security/)<br>
[Documentation Chart.js](https://www.chartjs.org/)<br>
[Tutoriel rédaction tests pytest-django](https://pytest-django.readthedocs.io/en/latest/)<br>
[Exemples de workflows CI](https://github.com/actions/starter%E2%80%91workflows)<br>
