# TP1 – Exercice 1 : Découverte de Docker

> **Objectif** : Prendre en main Docker Desktop et les commandes de base pour lancer, inspecter et nettoyer des conteneurs.

---

##  Étapes réalisées

### 1. Vérification de Docker Desktop
Docker Desktop est installé et en cours d’exécution (icône verte dans la barre des tâches).

### 2. Premier conteneur `hello-world`
```bash
docker run hello-world
```

### 3. Téléchargement de l’image `nginx:alpine` (sans lancer)
```bash
docker pull nginx:alpine
```

### 4. Liste des images locales
```bash
docker images
```

### 5. Lancement de nginx sur le port 8080 en arrière-plan
```bash
docker run -d -p 8080:80 --name my-nginx nginx:alpine
```
- `-d` : mode détaché (arrière-plan)
- `-p 8080:80` : redirection du port hôte vers le conteneur

### 6. Vérification dans le navigateur
Accès à http://localhost:8080 → page d’accueil de nginx affichée 

### 7. Affichage des logs
```bash
docker logs my-nginx
```
→ Montre les requêtes HTTP (ex: ```GET / HTTP/1.1```)

### 8. Liste de tous les conteneurs (actifs + arrêtés)
``` bash
docker ps -a
```

### 9. Arrêt et suppression du conteneur
```bash
docker stop my-nginx
docker rm my-nginx
```

### 10. Nettoyage des images inutilisées
```bash
docker system prune -a
```
→ Supprime les images non utilisées, les conteneurs arrêtés, etc.
