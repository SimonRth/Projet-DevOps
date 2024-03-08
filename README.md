# Projet_Monitoring

## commandes pour lancer le projet:

- Lancement de l'iamge grafana open-Source
```$ docker run -d -p 3000:3000 --name=grafana grafana/grafana-oss ```

- Verification de l'installation de l'image grafana
```$ docker ps```


^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Etape intermediaire si on veut faire avec un storage

-   Creation d"un storage pour grafana
```bash
$ docker volume create grafana-storage
```

-   Verifier la creation du storage 
```bash
$ docker volume inspect grafana-storage
```


- Demarer le docker grafana avec le storage 
```bash
$ docker run -d -p 3000:3000 --name=grafana \
  --volume grafana-storage:/var/lib/grafana \
  grafana/grafana-enterprise
```

^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Creation d'un dossier **data** pour stocker les donnees de la base de donnees
```bash
$ mkdir data
```
Lancrer grafana avec le dossier **data** pour stocker les donnees de la base de donnees
```bash
docker run -d -p 3000:3000 --name=grafana \
  --user "$(id -u)" \
  --volume "$PWD/data:/var/lib/grafana" \
  grafana/grafana-oss
```


