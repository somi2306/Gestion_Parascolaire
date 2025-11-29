# 🎓 Gestion Parascolaire

Ce projet consiste en une application web de gestion des clubs et événements parascolaires. Elle vise à centraliser et à simplifier la gestion des activités parascolaires au sein d’un établissement scolaire. L’application permet aux étudiants de découvrir les clubs, de s’inscrire à des événements, de suivre leurs activités et de communiquer entre eux. Les administrateurs et les responsables de clubs disposent d’outils pour gérer efficacement les clubs, les événements et la communication.

---

## 🏗 Architecture & Technologies

Le projet est conçu comme une application **MERN Stack** (MongoDB, Express, React, Node.js) :

### 🎨 Frontend (`frontend/`)
* **Framework** : React.js
* **Langage** : JavaScript (JSX)
* **Styling** : CSS natif (Fichiers dédiés dans `src/styles/`)
* **Structure** :
    * `components/` : Composants réutilisables (Connexion, Profil, etc.)
    * `styles/` : Feuilles de style CSS.

### ⚙️ Backend (`backend/`)
* **Serveur** : Node.js avec Express
* **Base de données** : MongoDB (Modélisation via Mongoose)
* **Authentification** : Basée sur des Tokens (Middleware `auth.js`)
* **Gestion des Fichiers** : Upload d'images (via Multer)
* **API REST** : Gestion des routes pour les étudiants, clubs et événements.

---

## 🚀 Installation et Configuration

### Prérequis
* **Node.js** (v14+ recommandé)
* **MongoDB** (Instance locale ou Atlas)
* **npm** (ou yarn)

### 1. Installation du Backend

> [!IMPORTANT]
> Le backend nécessite une connexion à une base de données MongoDB pour fonctionner.

1.  Accédez au dossier backend :
    ```bash
    cd backend
    ```
2.  Installez les dépendances :
    ```bash
    npm install
    ```
3.  **Configuration** :
    Le fichier `backend/config/.env` doit contenir vos variables d'environnement. Assurez-vous qu'il est présent et correctement rempli (Port, URL MongoDB, Secret JWT, etc.).
    *Exemple de contenu `.env` :*
    ```env
    PORT=5000
    MONGO_URI=
    JWT_SECRET=
    ```

### 2. Installation du Frontend

1.  Accédez au dossier frontend :
    ```bash
    cd ../frontend
    ```
2.  Installez les dépendances :
    ```bash
    npm install
    ```

---

## 💻 Démarrage de l'application

Pour lancer le projet, vous devez exécuter le backend et le frontend simultanément (dans deux terminaux séparés).

### Terminal 1 : Backend

```bash
cd backend
# Lance le serveur (par défaut souvent sur le port 5000)
npm run dev
```

### Terminal 2 : Frontend

```bash
cd frontend
npm run dev
```
L'interface utilisateur sera accessible via http://localhost:3000

---

## 📂 Structure du Projet

Voici un aperçu des dossiers clés :

| Dossier / Fichier | Description |
| :--- | :--- |
| **`backend/`** | |
| `├── app.js` | Point d'entrée de l'application serveur. |
| `├── models/` | Schémas de données (Club, Etudiant, Evenement, Forum). |
| `├── routes/` | Définition des endpoints API (connexion, profil, etc.). |
| `├── controllers/` | Logique métier (ex: `profilController.js`). |
| `├── middlewares/` | Gestion de l'auth et des uploads. |
| **`frontend/`** | |
| `├── src/components/` | Pages et composants React (Connexion, Profil). |
| `├── src/styles/` | Fichiers CSS (`connexion.css`, `profil.css`). |
| `├── public/` | Fichiers statiques (`index.html`, images). |

---

## 📝 Fonctionnalités

L'application offre des fonctionnalités distinctes selon le type d'utilisateur :

### 🌍 Pour les invités
* **Forum Commun** : Accéder au forum commun pour consulter les événements et activités des clubs.
* **Calendrier** : Visualiser le calendrier des événements avec des détails pour chaque événement (date, lieu, description).
* **Interaction** : Indiquer leur intérêt pour un événement via un bouton.

### 🎓 Pour les étudiants
* **Authentification** : S’authentifier avec leur email institutionnel et un mot de passe.
* **Gestion de Profil** : Accéder à leur profil et modifier leurs informations personnelles.
* **Gestion des Clubs** :
    * S’inscrire et se désinscrire des clubs.
    * Demander la création de nouveaux clubs.
* **Suivi d'Activités** : Suivre les clubs et événements auxquels ils sont inscrits.
* **Événements** : S’inscrire aux événements et recevoir des notifications de rappel.
* **Communication** : Participer au forum commun et aux forums privés des clubs.

