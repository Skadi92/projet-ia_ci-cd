# Compréhension du besoin 

Déployer une infrastructure VSCode boostée à l'IA afin de créer un environnement collaboratif de développement synchronisé par l'IA et géré par Github.


### VSCode

Le VSCode est hébergé en interne sur un serveur Linux quelconque, et profite d'une interface web pour le développement.
Une IA (Claude Code) est intégrée à VSCode pour assister les développeurs lors de la rédaction du code


### Agents IA

En plus de Claude Code pour VSCode, plusieurs autres modèles doivent être déployés : 

- Openclaw
- Codex
- Cursor
- Hermès

A voir quelle utilisation leur donner, et les spécificités de leur déploiement

### Github

Une pipeline CI/CD complète doit être mise en place, en y intégrant les bonnes pratiques de développement :

- Validation des commits
- Protection des variables sensibles
- Git Actions pour automatiser les process
- Git ignore configuré pour protéger l'infrastructure (prod)