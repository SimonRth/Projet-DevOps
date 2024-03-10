# Projet_Monitoring

Ce projet vise à mettre en place un système de monitoring à l'aide de Grafana, Docker, Prometheus, et Node Exporter. Le déploiement est simplifié grâce à l'utilisation de Docker Compose. En plus de la mise en place du système de surveillance, des tableaux de bord sont configurés dans Grafana pour visualiser les métriques collectées.

** Introduction **
Dans le domaine de la cybersécurité, la surveillance des systèmes est essentielle pour détecter les anomalies et garantir la disponibilité et la fiabilité des services. Ce projet nous a plu car il propose une solution de monitoring basée sur des outils open source, offrant une visibilité en temps réel sur les performances du système.

** Prérequis **
- machine Linux Ubuntu
- Docker ```sudo apt install docker```
- un IDE (ex: VsCode)


### Demmarer le projet:
Clonez le repository sur votre machine et entrez dedans.
Ensuite, créez un dossier "data" pour stoquer les données de Grafana.

Creation d'un dossier **data** pour stocker les donnees de la base de donnees
```bash
$ mkdir data
```
### Configuration de Prometheus et Node Exporter

- **Prometheus** est configuré via le fichier `prometheus.yml` pour scraper les métriques exposées par `node-exporter` et `cadvisor`. Assurez-vous que ce fichier est correctement configuré et accessible à Prometheus dans le conteneur.

- **Node Exporter** est un outil qui expose les métriques du système et du serveur pour être scrapées par Prometheus. Il est lancé automatiquement via `docker-compose` et accessible sur le port `9100`.


Pour simplifier le déploiement de Prometheus et cAdvisor, un fichier `docker-compose.yaml` est utilisé. Assurez-vous d'avoir ce fichier à la racine de votre projet.

- **Démarrage des services avec docker-compose**

  ```bash
  docker-compose up -d
  ```

Ce fichier `docker-compose.yaml` doit inclure la configuration pour Prometheus et cAdvisor, en plus de Grafana si vous souhaitez le gérer via docker-compose également.

Vous pouvez vérifier le bon foctionnement de vos Docker avec la commande ```docker ps``` 4 Docker devraient être entrain de tourner.

Allez sur ```http://localhost:3000``` pour acceder aux panneaux de Grafana.
Lors de votre première connexion les identifiants sont "admin" "admin".

**Configuration des Dashboards**
Des tableaux de bord peuvent être ajoutés dans Grafana pour visualiser les métriques collectées par Prometheus. Nous avons créé 3 dashboards. Un pour notre machine physique. Un pour docker register, et enfin un dédié aux besoins du projet docker. 

**Conclusion**
En utilisant Docker, Grafana, Prometheus et Node Exporter, ce projet permet de mettre en place facilement un système de monitoring robuste pour surveiller les performances des systèmes. La configuration flexible et les fonctionnalités de visualisation avancées offertes par Grafana permettent une surveillance efficace et proactive.

