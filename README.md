# Projet_Monitoring

Ce projet vise à mettre en place un système de monitoring à l'aide de Grafana, Docker, Prometheus, et Node Exporter. Le déploiement est simplifié grâce à l'utilisation de Docker Compose. En plus de la mise en place du système de surveillance, des tableaux de bord sont configurés dans Grafana pour visualiser les métriques collectées.

### Introduction 
Dans le domaine de la cybersécurité, la surveillance des systèmes est essentielle pour détecter les anomalies et garantir la disponibilité et la fiabilité des services. Ce projet nous a plu car il propose une solution de monitoring basée sur des outils open source, offrant une visibilité en temps réel sur les performances du système.

### Prérequis
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
### Déploiement des Services

- Utilisez le fichier `docker-compose.yaml` à la racine de votre projet pour déployer Grafana, Prometheus, cAdvisor, et Node Exporter. Cette configuration simplifie le processus de lancement et assure que tous les services nécessaires sont correctement configurés et interconnectés.

- Lancement des services : Exécutez la commande suivante pour démarrer tous les services définis dans votre fichier `docker-compose.yaml`.

  ```bash
  docker-compose up -d
  ```

## Accès et Utilisation

- **Grafana** : Accédez à Grafana sur <http://localhost:3000> pour visualiser les tableaux de bord de monitoring.
- **Prometheus** : Prometheus, accessible sur <http://localhost:9090>, est utilisé pour le scraping des métriques et leur stockage.
- **cAdvisor** : cAdvisor fournit des métriques sur l'utilisation des ressources par les conteneurs et est accessible sur <http://localhost:8080>.
- **Node Exporter** : Node Exporter expose les métriques du système et du serveur, facilitant leur scraping par Prometheus.

Vous pouvez vérifier le bon foctionnement de vos Docker avec la commande ```docker ps``` 4 Docker devraient être entrain de tourner.


**Configuration des Dashboards**
Des tableaux de bord peuvent être ajoutés dans Grafana pour visualiser les métriques collectées par Prometheus. Nous avons créé 3 dashboards. Un pour notre machine physique. Un pour docker register, et enfin un dédié aux besoins du projet docker. 

**Conclusion**
En utilisant Docker, Grafana, Prometheus et Node Exporter, ce projet permet de mettre en place facilement un système de monitoring robuste pour surveiller les performances des systèmes. La configuration flexible et les fonctionnalités de visualisation avancées offertes par Grafana permettent une surveillance efficace et proactive.

