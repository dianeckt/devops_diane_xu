# devops_project_CHANKYTO_CHEN
devops project 2022-2023


## Auteurs
* Diane CHAN KY TO
* Xu CHEN


## Travaux effectués
1. Création d'une application web 
    - langage : javascript
    - gestion d'utilisateurs : création, lecture, mise à jour, suppression
    - utilisateurs stockés dans une database avec Redis
    - tests avec npm et Redis : unité (création des utilisateurs), API (gestion des utilisateurs via l'API), 
        configuration (chargement de différentes configurations), connexion (à Redis)
    - health check endpoint garantissant que l'application soit fonctionnelle
2. Création d'un script de bienvenue
3. CI/CD avec la plateforme de déploiement Heroku
4. Configuration et approvisionnement d'un environnement virtuel et exécution de l'application en utilisant l'approche IaC
    - Imperative en utilisant Vagrant avec Shell 
    - Declarative en installant GitLab et utilisant Vagrant et Ansible
    - Declarative en configurant des health check 
5. Construire une image de l'application avec Docker
6. Container orchestration en utilisant Docker Compose
7. Container orchestration en utilisant Kubernetes 
    - Kubernetes déploiement
    - déploiement en utilisant un fichier Manifest yaml
    - création d'un persistent volume et persistent volume claim
8. Création d'un service mesh avec Istio
9. Surveillance de notre application conteneurisée



## Captures d'écran des travaux effectués
Toutes les captures d'écran ont été placées dans le document Word "Devops project rapport.odt" de ce repo. Elles sont les preuves visuelles du bon fonctionnement de nos travaux.


## Liens nécessaires avec les plateformes et outils intégrés
- Redis                     
- npm                       
- Heroku                    
- Vagrant                   
- Docker 
- Kubernetes
- Istio
- Prometheus 
- Grafana


## Instructions/Commandes pour procéder à :
1. Installation/Préparation de notre environnement 
    - Veillez à avoir téléchargé tous les outils listés ci-dessus
    - Lancer le server redis : 'redis-server'
    - Lancer Docker 
    - Lancer minikube avec Docker comme driver 'minikube start --driver=docker' puis vérification 'minikube status'

2. Lancer le script de bienvenue (dans lab-3) : 'npm run bonjour' 

3. Lancement des tests (dans lab-3) 
    - manuellement : 'npm test'
    - automatique : à chaque commit sur la branche main avec Heroku

4. Configuration et approvisionnement d'un environnement virtuel et exécution de l'application en utilisant l'approche IaC (dans vagrantfile)
    - Initialisation : 'vagrant init'
    - Lancement des fichiers de configuration : 'vagrant up'
    - Lancement de la VM : 'vagrant ssh'

5. Constuire une image de l'application (dans lab-6-docker/bienvenue_docker)
    - Build : 'docker build -t bienvenue_docker .'
    - Run : 'docker run -p 12345:2309 -d bienvenue_docker'
    - Vérification : ouvrir dans le navigateur la page 'http://localhost:12345/'

6. Récupération de l'image créée précédemment via un autre pc
    - récupération de l'image : 'docker pull dckt/bienvenue_docker'
    - Run : 'docker run -p 12345:2309 -d dckt/bienvenue_docker'
    - Vérification : ouvrir dans le navigateur la page 'http://localhost:12345/'

7. Container orchestration avec Docker (dans lab-6-docker/bienvenue-docker-compose)
    - Build : 'docker-compose up'
    - Vérification : ouvrir dans le navigateur la page 'http://localhost:1010/'

8. Container orchestration avec Kubernetes (dans lab-6-docker/bienvenue-docker-compose)
    - Cration d'un nouveau déploiement : 'kubectl create deployment kubernetes-bootcamp --image=gcr.io/google-samples/kubernetes-bootcamp:v1'
    - Utilisation du service : 'minikube service kubernetes-bootcamp-service'

9. Déploiement avec un Manifest yaml (dans lab-7-docker-docker_orchestration_Kubernetes)
    - Application du déploiement et du service : 'kubectl apply -f deployment.yaml' et 'kubectl apply -f service.yaml'
    - Utilisation du service : 'minikube service kubernetes-bootcamp-service'

10. Création d'un persistent volume et persistent volume claim (dans lab-7-docker-docker_orchestration_Kubernetes)
    - Application du persistent volume : 'kubectl apply -f pv_volume.yaml'  
    - Application du persistent volume claim : 'kubectl apply -f https://k8s.io/examples/pods/storage/pv-claim.yaml'  



