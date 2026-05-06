


Pour l'ajout de Watcher Remote (dans le docker compose) :

```
services:
  whatsupdocker:
    image: getwud/wud
    ...
    environment:
        - WUD_WATCHER_MYREMOTEHOST_HOST=myremotehost 
```