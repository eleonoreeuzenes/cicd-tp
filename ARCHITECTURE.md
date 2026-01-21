# Architecture du Projet

## Structure du Projet

```
.
├── .eslintignore
├── .eslintrc.js
├── .gitignore
├── .nvmrc
├── README.md
├── package-lock.json
├── package.json
├── src
│   ├── greeting.js
│   └── server.js
└── tests
    ├── e2e
    │   └── e2e.test.js
    ├── integration
    │   └── app.test.js
    └── unit
        └── greeting.test.js
```

## Description des Composants

### `src/greeting.js`
Ce fichier contient la logique métier pour générer un message de salutation. La fonction `getGreeting` prend un paramètre `name` et retourne un message de salutation personnalisé.

### `src/server.js`
Ce fichier contient la configuration du serveur et les endpoints de l'API. Il utilise le module `greeting.js` pour fournir des fonctionnalités de salutation via des endpoints HTTP.

## Endpoints Disponibles

### GET `/hello/:name?`
Retourne un message de salutation. Le paramètre `name` est optionnel.

**Paramètres :**
- `name` (optionnel) : Le nom à inclure dans le message de salutation.

**Exemples :**
- `GET /hello` → "Hello world!"
- `GET /hello/Alice` → "Hello world! From Alice"

### POST `/hello`
Retourne un message de salutation avec le nom fourni dans l'en-tête `x-name`.

**En-têtes :**
- `x-name` : Le nom à inclure dans le message de salutation.

**Exemple :**
- `POST /hello` avec `x-name: Alice` → "Hello world! From Alice"

## Tests

### Tests Unitaires
Les tests unitaires sont situés dans le répertoire `tests/unit`. Ils testent les fonctions individuelles du projet, comme la fonction `getGreeting` dans `greeting.js`.

### Tests d'Intégration
Les tests d'intégration sont situés dans le répertoire `tests/integration`. Ils testent l'interaction entre différents composants du projet.

### Tests End-to-End
Les tests end-to-end sont situés dans le répertoire `tests/e2e`. Ils testent le comportement global de l'application, y compris les endpoints de l'API.

## Configuration

### `.eslintrc.js`
Ce fichier contient la configuration d'ESLint pour le projet, définissant les règles de linting et les standards de codage.

### `.nvmrc`
Ce fichier spécifie la version de Node.js à utiliser pour le projet.

### `package.json`
Ce fichier contient les métadonnées du projet, les dépendances, et les scripts pour exécuter et tester le projet.
