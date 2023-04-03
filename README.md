1- Fichier Dockerfile
    FROM nginx
    WORKDIR /app
    COPY . /usr/share/nginx/html
memoire - Créer un Repository sur github
    https://github.com/Samir04031977/site
    Copier le projet vers github
    git init
    git remote add origin https://github.com/Samir04031977/site.git
    git branch -M main
    git add .
    git commit -m "init project"
    git push -u origin main
2- Construire l'image
    docker build -t samir1977/site .
3- Pousser l'image vers Dockerhub
    docker push samir1977/site
4- Deployer l'appli
    kubectl create deployment site-deployment --image samir1977/site
    kubectl expose deployment/site1-deployment --type LoadBalancer --port 80
    minikube service site-deployment
    kubectl scale deployment/site-deployment --replicas 6

