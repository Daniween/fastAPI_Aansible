# FastAPI Hello World avec Docker déployée avec Ansible

## 📌 Description du Projet

Ce projet est une API simple construite avec **FastAPI**, qui expose une route `GET /` renvoyant un message `"Hello, World!"`.  
Elle est conteneurisée avec **Docker**, et automatiquement **déployée sur un serveur distant via Ansible** avec **GitHub Actions**.

---

## 🚀 Prérequis

Avant de démarrer en local ou de déployer, assurez-vous d'avoir installé :

- [Python 3.10+](https://www.python.org/downloads/)
- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/index.html) (pour déploiement manuel)

---

## 📂 Structure du Projet

```
fastapi-docker-app/
├── app/                         # Code source FastAPI
    └── main.py
├── Dockerfile                   # Dockerfile pour builder l'image
├── docker-compose.yml           # Configuration Docker Compose
├── .dockerignore
├── .gitignore
└── ansible/                     # Dossier Ansible pour le déploiement
    ├── deploy_app.yml           # Playbook principal
    ├── inventory                # Fichier d’inventaire
    └── roles/
        └── deploy/              # Rôle Ansible dédié au déploiement
            ├── tasks/
                └── main.yml
            └── vars/
                └── main.yml
```

## 🏗️ Installation et Exécution

### 1️⃣ Cloner le dépôt

```bash
git clone git@github.com:Daniween/FastAPI_Ansible.git
cd FastAPI_Ansible
```

### 2️⃣ Démarrer le projet avec Docker Compose

Construire et exécuter l'application en mode développement avec rechargement automatique :

```bash
docker-compose up --build -d
```

### 3️⃣ Accéder à l'API

- **Endpoint principal** : [http://127.0.0.1:8000](http://127.0.0.1:8000)

### 4️⃣ Arrêter l'application

```bash
docker-compose down
```

## 🚀 Déploiement automatisé avec GitHub Actions + Ansible

Le déploiement est déclenché automatiquement à chaque push sur main.
Il utilise :

GitHub Actions

Ansible

SSH (clé privée configurée dans les GitHub Secrets)

## 🔐 Secrets requis dans GitHub :

| Clé             | Description                                 |
| --------------- | ------------------------------------------- |
| SSH_PRIVATE_KEY | Clé privée SSH pour se connecter au serveur |
| SSH_HOST        | IP ou hostname du serveur distant           |

---

✨ **Happy Coding!** 🚀
