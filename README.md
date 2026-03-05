# Payment API — Spring Boot

Microservice REST développé avec Spring Boot pour la gestion des paiements dans une architecture microservices.
Ce service communique avec les autres services du système (reservations).

Les specs communes des APIs sont dans le fichier TML.yml ainsi que les schémas des dépendances fais en cours qui sont dans les fichiers specs.png

---

## Description

Payment API est responsable de :

* Créer un paiement
* Consulter un ou plusieurs paiements
* Supprimer un paiement
* Mettre à jour le statut d’un paiement

Ce microservice s’intègre dans l’écosystème suivant :

* gateway
* user_api
* reservation_api
* payment_api (ce projet)

---

## Stack technique

* Java 17+
* Spring Boot
* Spring Web
* Spring Data JPA
* Gradle
* Base de données SQL (MariaDB)
* Swagger / OpenAPI

---

## Lancement du projet

### 1) Cloner le repository

```bash
git clone git@github.com:timo0135/api-payment.git
```

### 2) Lancer la base de données en local avec Docker compose

```bash
docker compose up -d
```

### 3) URL par défaut et lancent l'API avec IntelliJ

```
http://localhost:8080
```

---

## 📂 Structure du projet

```
payment-api/
│
├── src/main/java/com/payment/
│   ├── controllers/
│   ├── dtos/
│   ├── entities/
│   ├── mappers/
│   ├── repositories/
│   ├── services/
│   │   │
│   │   └── impl/
│   └── App.java
│
├── src/main/resources/
│   ├── application.properties
│
├── pom.xml
└── README.md

```

---

## 📡 Endpoints
(voir le swagger en lancent le projet à l'url /swagger-ui/index.html)

## 🗄 Configuration base de données

Exemple avec Mariadb (développement) dans `application.properties` :

```properties
spring.datasource.url=jdbc:mariadb://localhost:3306/payement_db
spring.datasource.username=root
spring.datasource.password=root
spring.datasource.driver-class-name=org.mariadb.jdbc.Driver
spring.jpa.database-platform=org.hibernate.dialect.MariaDBDialect
spring.jpa.show-sql=true
spring.jpa.hibernate.ddl-auto=update
```

---

## 📘 Documentation Swagger

Disponible après lancement :

```
http://localhost:8080/swagger-ui.html
```

ou

```
http://localhost:8080/swagger-ui/index.html
```

---

## 🔗 Intégration microservices

Payment API est utilisé par :

* reservation_api → associe un paiement à une réservation

---

## 👨‍💻 Auteur

Timothée BENCHERGUI - Léa CRENN-DURIF - Maxence THOMAS

---

## 📄 Licence

Licence Open Source (MIT License).
