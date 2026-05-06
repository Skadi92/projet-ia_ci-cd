Conf simpliste de base :
```
services:
  whatsupdocker:
    image: getwud/wud
	container_name: wud
	volumes:
	  - /var/run/docker.sock:/var/run/docker.sock:ro
	ports:
	  - 3030:3000
	environment:
	  - WUD_WATCHER_LOCAL_SOCKET=/var/run/docker.sock
```

Pour l'ajout de Watcher Remote (dans le docker compose) :

```
services:
  whatsupdocker:
    image: getwud/wud
    container_name: wud
	volumes:
	  - /var/run/docker.sock:/var/run/docker.sock:ro
	ports:
	  - 3030:3000
    environment:
      - WUD_WATCHER_MYREMOTEHOST_HOST=myremotehost 
      - WUD_WATCHER_VM1_HOST=172.16.131.11
      - WUD_WATCHER_VM1_PORT=2375
	  - WUD_WATCHER_VM1_CRON=0 1 * * *
	  - WUD_WATCHER_VM1_WATCHALL=true
	restart: unless-stopped
```

Config SMTP (envoi de mail automatique d'update)

```
- WUD_TRIGGER_SMTP_GMAIL_HOST=smtp.gmail.com
- WUD_TRIGGER_SMTP_GMAIL_PORT=465
- WUD_TRIGGER_SMTP_GMAIL_USER=twyrms@gmail.com
- WUD_TRIGGER_SMTP_GMAIL_PASS=[Password]
- WUD_TRIGGER_SMTP_GMAIL_FROM=[Email sender]
- WUD_TRIGGER_SMTP_GMAIL_TO=[Email r]
- WUD_TRIGGER_SMTP_GMAIL_TLS_ENABLED=true
- WUD_TRIGGER_SMTP_GMAIL_SIMPLETITLE=Docker - Container $${container.name} can be updated
- WUD_TRIGGER_SMTP_GMAIL_SIMPLEBODY=Docker Container $${name} can be updated from $${local} to $${remote}
```

L'auto update de containers n'est **pas recommandée** et **non-native** à WUD sur des Remote Hosts, uniquement en local.

![[Pasted image 20260506181855.png]]

Watcher local activé

![[Pasted image 20260506182134.png]]

Watcher remote activé sur la VM de test

![[Pasted image 20260506182201.png]]

Containers surveillés par WUD, avec version de chaque et mise à jour disponible.

![[Pasted image 20260506182315.png]]
Trigger de notification mail activé, avec option de test

![[Pasted image 20260506182504.png]]
Installation de nginx 1.25, ancienne version de Nginx, qui est censée être reconnue comme telle par WUD.

![[Pasted image 20260506182605.png]]
Une fois le container activé, un mail est envoyé avec l'update disponible précisée.