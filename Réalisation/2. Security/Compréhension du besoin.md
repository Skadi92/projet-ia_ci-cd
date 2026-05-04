# Compréhension du besoin

Déployer une solution de WAF (Web Application Filter) afin de router le trafic internet vers les applications internes, journaliser les connexions et protéger l'infrastructure de l'association

**Solution apportée** : BunkerWeb - https://www.bunkerweb.io

### Architecture actuelle

Nginx Proxy Manager (NPM) fait office de reverse proxy pour permettre aux clients d'accéder aux ressources de l'association.
NPM écoute sur les ports **80** et **443** et transmet à plusieurs dizaines d'applications (dockers) les requêtes.

Traefik redirige les requêtes envoyées par NPM vers Easy4IA, ce qui ajoute une couche de complexité.

### Proposition

#### 1. Phase Pilote

Déployer BunkerWeb en ajoutant une nouvelle couche de redirection : entre le pare-feu et NPM.
Rediriger le trafic depuis internet en 80 et 443 vers BunkerWeb, qui redirige à son tour sur les mêmes ports à NPM.
Ajouter une redirection à Traefik directement (sans passer par NPM)