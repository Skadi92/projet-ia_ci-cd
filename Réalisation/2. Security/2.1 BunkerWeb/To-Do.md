# To-do

- [ ] Consulter la documentation pour comprendre les possibilités et le fonctionnement de la solution
- [ ] Consulter Alex sur l'infrastructure exacte à mettre en place
- [ ] Créer un schéma d'infrastructure suite à la discussion
- [ ] Définir les ports entrée/sortie à paramétrer
- [x] Créer le docker-compose.yml Phase Pilote (HTTP uniquement, SSL géré par NPM)
- [ ] Récupérer le nom du réseau Docker de NPM (`docker network ls`) et remplacer `RESEAU_NPM`
- [ ] Récupérer le nom du réseau Docker de Traefik et remplacer `RESEAU_TRAEFIK`
- [ ] Remplacer `DOMAINE.fr` par le vrai domaine dans le docker-compose.yml
- [ ] Remplacer `CONTENEUR_NPM` et `CONTENEUR_TRAEFIK` par les noms réels des conteneurs
- [ ] Copier `.env.example` en `.env` et définir `BW_DB_PASSWORD`
- [ ] Tester le déploiement : `docker compose up -d`
- [ ] Vérifier les logs : `docker compose logs -f bunkerweb`
- [ ] Configurer la règle pare-feu : port 80 externe → port 10080 BunkerWeb
