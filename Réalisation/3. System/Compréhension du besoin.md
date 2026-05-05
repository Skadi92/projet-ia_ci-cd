# Compréhension du besoin

Déployer une solution de mise à jour d'images de containers Docker. Cette idée vient d'un besoin de conformité aux standards de sécurité informatique. Les applicatifs installés actuellement sont pour la plupart out-of-date, renforçant le risque d'attaque.

**Solution apportée :** WhatsUpDocker (WUD) - https://getwud.github.io/wud/#/

### Points de vigilance

Redéployer tous les dockers avec l'image la plus récente peut avoir des répercussions sur le reste de l'infrastructure.
Il ne doit pas y avoir de longues périodes de maintenance (prod)
