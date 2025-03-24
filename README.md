# TP CI/CD - API REST avec Express et MongoDB

Ce projet est une API REST développée avec Express.js et MongoDB, dans le cadre d'un TP sur l'intégration continue et le déploiement continu (CI/CD).

## 👥 Auteurs

- Youva Houche
- Samy Bakouche
- Fara Hovor
- Hugo Antonini Lounes

## 🚀 Prérequis

- Node.js (version >= 18.0.0)
- Docker et Docker Compose
- MongoDB (fourni via Docker)

## 🛠️ Installation

1. Clonez le repository :
```bash
git clone [URL_DU_REPO]
cd tp-ci-cd-backend
```

2. Installez les dépendances :
```bash
npm install
```

3. Créez un fichier `.env` à la racine du projet avec les variables suivantes :
```env
PORT=3000
MONGODB_URI=mongodb://mongodb:27017/base
```

## 🏃‍♂️ Lancement du projet

### Option 1 : Avec Docker (recommandé)

```bash
docker-compose up --build
```

Cette commande va :
- Construire l'image Docker
- Démarrer le conteneur MongoDB
- Démarrer l'application Node.js
- Exposer l'API sur le port 3000

### Option 2 : Sans Docker

1. Assurez-vous que MongoDB est en cours d'exécution
2. Lancez l'application :
```bash
# Pour le développement (avec nodemon)
npm run dev

# Pour la production
npm start
```

## 📝 Scripts disponibles

- `npm start` : Lance l'application en mode production
- `npm run dev` : Lance l'application en mode développement avec nodemon
- `npm test` : Lance les tests (à implémenter)

## 🔧 Technologies utilisées

- Node.js
- Express.js
- MongoDB
- Docker
- Docker Compose

## 📚 Documentation de l'API

L'API est accessible à l'adresse : `http://localhost:3000`

### Endpoints disponibles

- `GET /` : Page d'accueil
- `GET /health` : Vérification de l'état de l'API

### Gestion des Items

#### Créer un item
```http
POST /items
Content-Type: application/json

{
    "name": "Nom de l'item"
}
```

**Réponse (201 Created)**
```json
{
    "name": "Nom de l'item",
    "createdAt": "2024-03-24T12:00:00.000Z"
}
```

#### Récupérer tous les items
```http
GET /items
```

**Réponse (200 OK)**
```json
[
    {
        "name": "Nom de l'item",
        "createdAt": "2024-03-24T12:00:00.000Z"
    }
]
```

### Codes d'erreur

- `400 Bad Request` : Données invalides
- `404 Not Found` : Ressource non trouvée
- `500 Internal Server Error` : Erreur serveur