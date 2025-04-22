Voici une traduction en français du fichier `README.md` :

---

# Architecture Propre Backend en Go

Un projet d'architecture propre backend en Go (Golang) utilisant Gin, MongoDB, un middleware d'authentification JWT, des tests, et Docker.

![Architecture Propre Backend en Go](https://github.com/amitshekhariitbhu/go-backend-clean-architecture/blob/main/assets/go-backend-clean-architecture.png?raw=true)

**Vous pouvez utiliser ce projet comme modèle pour construire votre projet backend en langage Go à partir de ce projet.**

Avant de créer ce projet, j'ai exploré plus de 20 projets liés à l'architecture propre en Go (Golang) sur GitHub.

Merci à tous ces projets, j'ai beaucoup appris de chacun d'entre eux. Comme je le dis souvent :

> La meilleure façon d'apprendre à coder, c'est de coder. Mais pour bien coder, il faut aussi lire du bon code. Prenez l'habitude de lire du bon code. Vous pouvez trouver de nombreux projets open-source sur GitHub et commencer [...]

Ensuite, pour la partie implémentation, j'ai combiné toutes mes idées, expériences et apprentissages de ces projets pour créer ce projet.

Et comme toujours, j'aimerais recevoir des retours sur mon projet. Cela aide tout le monde et surtout moi-même.

Apprenez-en plus sur l'architecture de ce projet en détail grâce aux blogs mentionnés ci-dessous :

- [Architecture Propre Backend en Go](https://outcomeschool.com/blog/go-backend-clean-architecture)
- [Middleware d'authentification JWT en Go](https://outcomeschool.com/blog/go-jwt-authentication-middleware)
- [Configuration avec Viper en Go](https://outcomeschool.com/blog/configuration-with-viper-in-go)
- [Tests avec Testify et Mockery en Go](https://outcomeschool.com/blog/test-with-testify-and-mockery-in-go)
- [Normalisation vs Dénormalisation des bases de données](https://outcomeschool.com/blog/database-normalization-vs-denormalization)

## Couches d'architecture du projet

- Routeur
- Contrôleur
- Cas d'utilisation
- Dépôt (Repository)
- Domaine

![Diagramme de l'architecture propre backend en Go](https://github.com/amitshekhariitbhu/go-backend-clean-architecture/blob/main/assets/go-backend-arch-diagram.png?raw=true)

## À propos de moi

Bonjour, je suis Amit Shekhar, co-fondateur de [Outcome School](https://outcomeschool.com) • IIT 2010-14 • J'ai enseigné et mentoré de nombreux développeurs, et leurs efforts leur ont permis d'obtenir des emplois techniques bien rémunérés, hel [...]

Vous pouvez me contacter sur :

- [Twitter](https://twitter.com/amitiitbhu)
- [YouTube](https://www.youtube.com/@amitshekhar)
- [LinkedIn](https://www.linkedin.com/in/amit-shekhar-iitbhu)
- [GitHub](https://github.com/amitshekhariitbhu)

## Playlist sur la conception de systèmes sur YouTube

- [Qu'est-ce que la conception de systèmes ?](https://www.youtube.com/watch?v=i4YWRY3hsdA)
- [Conception de la timeline Twitter avec l'approche Fanout - Conception de systèmes](https://www.youtube.com/watch?v=_7qHGfwgPz0)
- [Requête HTTP vs Long-Polling HTTP vs WebSocket vs Server-Sent Events](https://www.youtube.com/watch?v=8ksWRX4xV-s)
- [Service de téléchargement de vidéos YouTube - Conception de systèmes](https://www.youtube.com/watch?v=N0vvJTkokZc)
- [Qu'est-ce que le hachage cohérent ?](https://www.youtube.com/watch?v=dV5cIm9T3ss)
- [Estimation de la capacité : Calcul approximatif - Twitter](https://www.youtube.com/watch?v=yrbKxzXm6_Q)

## Principaux paquets utilisés dans ce projet

- **gin** : Gin est un framework web HTTP écrit en Go (Golang). Il propose une API similaire à Martini avec de bien meilleures performances -- jusqu'à 40 fois plus rapide. Si vous avez besoin de performances exceptionnelles, adoptez Gin.
- **mongo go driver** : Le driver officiel Golang pour MongoDB.
- **jwt** : Les JSON Web Tokens sont une méthode standard ouverte (RFC 7519) pour représenter des revendications de manière sécurisée entre deux parties. Utilisé pour les tokens d'accès et de rafraîchissement.
- **viper** : Pour charger la configuration depuis le fichier `.env`. Configuration en Go avec des fonctionnalités étendues. Permet de trouver, charger et désérialiser un fichier de configuration au format JSON, TOML, YAML, HCL, INI, envfile ou propriétés Java.
- **bcrypt** : Le package bcrypt implémente l'algorithme de hachage adaptatif bcrypt.
- **testify** : Une boîte à outils avec des assertions et des mocks qui s'intègre bien avec la bibliothèque standard.
- **mockery** : Un générateur automatique de code mock pour Golang utilisé dans les tests.
- Consultez plus de paquets dans `go.mod`.

### Flux de requêtes API publiques sans middleware d'authentification JWT

![Flux de requêtes API publiques](https://github.com/amitshekhariitbhu/go-backend-clean-architecture/blob/main/assets/go-arch-public-api-request-flow.png?raw=true)

### Flux de requêtes API privées avec middleware d'authentification JWT

> Middleware d'authentification JWT pour la validation des tokens d'accès.

![Flux de requêtes API privées](https://github.com/amitshekhariitbhu/go-backend-clean-architecture/blob/main/assets/go-arch-private-api-request-flow.png?raw=true)

### Comment exécuter ce projet ?

Nous pouvons exécuter ce projet d'architecture propre backend en Go avec ou sans Docker. Voici les deux méthodes pour exécuter ce projet.

- Clonez ce projet

```bash
# Déplacez-vous dans votre espace de travail
cd votre-espace-de-travail

# Clonez ce projet dans votre espace de travail
git clone https://github.com/amitshekhariitbhu/go-backend-clean-architecture.git

# Déplacez-vous dans le répertoire racine du projet
cd go-backend-clean-architecture
```

#### Exécution sans Docker

- Créez un fichier `.env` similaire à `.env.example` dans le répertoire racine avec votre configuration.
- Installez `go` si ce n'est pas déjà fait sur votre machine.
- Installez `MongoDB` si ce n'est pas déjà fait sur votre machine.
- Important : Changez `DB_HOST` en `localhost` (`DB_HOST=localhost`) dans le fichier de configuration `.env`. `DB_HOST=mongodb` n'est nécessaire que lorsque vous utilisez Docker.
- Exécutez `go run cmd/main.go`.
- Accédez à l'API via `http://localhost:8080`.

#### Exécution avec Docker

- Créez un fichier `.env` similaire à `.env.example` dans le répertoire racine avec votre configuration.
- Installez Docker et Docker Compose.
- Exécutez `docker-compose up -d`.
- Accédez à l'API via `http://localhost:8080`.

### Comment exécuter les tests ?

```bash
# Exécutez tous les tests
go test ./...
```

### Comment générer le code mock ?

Dans ce projet, pour les tests, nous devons générer du code mock pour les cas d'utilisation, les dépôts et la base de données.

```bash
# Générez le code mock pour les cas d'utilisation et les dépôts
mockery --dir=domain --output=domain/mocks --outpkg=mocks --all

# Générez le code mock pour la base de données
mockery --dir=mongo --output=mongo/mocks --outpkg=mocks --all
```

Chaque fois que vous apportez des modifications aux interfaces de ces cas d'utilisation, dépôts ou bases de données, vous devez exécuter la commande correspondante pour régénérer le code mock pour les tests.

### Structure complète des dossiers du projet

```
.
├── Dockerfile
├── api
│   ├── controller
│   │   ├── login_controller.go
│   │   ├── profile_controller.go
│   │   ├── profile_controller_test.go
│   │   ├── refresh_token_controller.go
│   │   ├── signup_controller.go
│   │   └── task_controller.go
│   ├── middleware
│   │   └── jwt_auth_middleware.go
│   └── route
│       ├── login_route.go
│       ├── profile_route.go
│       ├── refresh_token_route.go
│       ├── route.go
│       ├── signup_route.go
│       └── task_route.go
├── bootstrap
│   ├── app.go
│   ├── database.go
│   └── env.go
├── cmd
│   └── main.go
├── docker-compose.yaml
├── domain
│   ├── error_response.go
│   ├── jwt_custom.go
│   ├── login.go
│   ├── profile.go
│   ├── refresh_token.go
│   ├── signup.go
│   ├── success_response.go
│   ├── task.go
│   └── user.go
├── go.mod
├── go.sum
├── internal
│   └── tokenutil
│       └── tokenutil.go
├── mongo
│   └── mongo.go
├── repository
│   ├── task_repository.go
│   ├── user_repository.go
│   └── user_repository_test.go
└── usecase
    ├── login_usecase.go
    ├── profile_usecase.go
    ├── refresh_token_usecase.go
    ├── signup_usecase.go
    ├── task_usecase.go
    └── task_usecase_test.go
```

### Documentation de l'API de l'architecture propre backend en Go

<a href="https://documenter.getpostman.com/view/391588/2s8Z75S9xy" target="_blank">
    <img alt="Bouton Voir la documentation de l'API" src="https://github.com/amitshekhariitbhu/go-backend-clean-architecture/blob/main/assets/button-view-api-docs.png?raw=true" width="200" height="60"/>
</a>

### Exemple de requêtes et réponses API

- Inscription

  - Requête

  ```
  curl --location --request POST 'http://localhost:8080/signup' \
  --data-urlencode 'email=test@gmail.com' \
  --data-urlencode 'password=test' \
  --data-urlencode 'name=Test Name'
  ```

  - Réponse

  ```json
  {
    "accessToken": "access_token",
    "refreshToken": "refresh_token"
  }
  ```

- Connexion

  - Requête

  ```
  curl --location --request POST 'http://localhost:8080/login' \
  --data-urlencode 'email=test@gmail.com' \
  --data-urlencode 'password=test'
  ```

  - Réponse

  ```json
  {
    "accessToken": "access_token",
    "refreshToken": "refresh_token"
  }
  ```

- Profil

  - Requête

  ```
  curl --location --request GET 'http://localhost:8080/profile' \
  --header 'Authorization: Bearer access_token'
  ```

  - Réponse

  ```json
  {
    "name": "Test Name",
    "email": "test@gmail.com"
  }
  ```

- Création de tâche

  - Requête

  ```
  curl --location --request POST 'http://localhost:8080/task' \
  --header 'Authorization: Bearer access_token' \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --data-urlencode 'title=Test Task'
  ```

  - Réponse

  ```json
  {
    "message": "Task created successfully"
  }
  ```

- Récupération des tâches

  - Requête

  ```
  curl --location --request GET 'http://localhost:8080/task' \
  --header 'Authorization: Bearer access_token'
  ```

  - Réponse

  ```json
  [
    {
      "title": "Test Task"
    },
    {
      "title": "Test Another Task"
    }
  ]
  ```

- Rafraîchissement du token

  - Requête

  ```
  curl --location --request POST 'http://localhost:8080/refresh' \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --data-urlencode 'refreshToken=refresh_token'
  ```

  - Réponse

  ```json
  {
    "accessToken": "access_token",
    "refreshToken": "refresh_token"
  }
  ```

### À faire

- Améliorations basées sur les retours.
- Ajouter plus de cas de tests.
- Toujours essayer de mettre à jour avec la dernière version des paquets utilisés.

## Si ce projet vous aide de quelque manière que ce soit, montrez votre amour ❤️ en mettant une ⭐ sur ce projet ✌️

### Licence

```
   Copyright (C) 2024 Amit Shekhar

   Sous licence Apache, version 2.0 (la "Licence").
   Vous ne pouvez pas utiliser ce fichier sauf conformément à la Licence.
   Vous pouvez obtenir une copie de la Licence à l'adresse suivante :

       http://www.apache.org/licenses/LICENSE-2.0

   Sauf si requis par la loi applicable ou convenu par écrit, le logiciel
   distribué sous la Licence est distribué "EN L'ÉTAT",
   SANS GARANTIE NI CONDITIONS D'AUCUNE SORTE, explicites ou implicites.
   Consultez la Licence pour plus de détails concernant les autorisations
   et les limitations dans le cadre de la Licence.
```

### Contribuer à l'architecture propre backend en Go

Toutes les demandes de pull request sont les bienvenues.

--- 

N'hésitez pas à me dire si vous avez besoin d'autres précisions ou d'une autre aide !
