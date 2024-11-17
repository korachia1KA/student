Projet : Gestion des Étudiants

Ce projet propose une API REST permettant de gérer les informations des étudiants en utilisant une base de données MySQL.

Fonctionnalités
L'API expose les fonctionnalités suivantes :

Ajouter un étudiant :
POST /students/save
Le corps de la requête doit contenir un objet JSON représentant l'étudiant à ajouter.

Supprimer un étudiant :
DELETE /students/delete/{id}
Permet de supprimer un étudiant à partir de son identifiant.

Récupérer tous les étudiants :
GET /students/all
Cette requête renvoie la liste complète des étudiants.

Compter le nombre total d'étudiants :
GET /students/count
Renvoie le nombre total d'étudiants enregistrés dans la base de données.

Compter les étudiants par année de naissance :
GET /students/byYear
Cette requête permet de compter le nombre d'étudiants regroupés par année de naissance.

Architecture du Projet
Le projet est structuré comme suit :

com.example.student_management.entities : Contient les entités JPA, en particulier l'entité Student.

com.example.student_management.repositories : Contient l'interface StudentRepository, qui gère les opérations sur les étudiants dans la base de données.

com.example.student_management.services : Contient la logique métier, en particulier le service StudentService, qui gère les règles de gestion liées aux étudiants.

com.example.student_management.controllers : Contient le contrôleur StudentController, qui expose les endpoints REST.

StudentManagementApplication.java : La classe principale de l'application, responsable du démarrage de l'application Spring Boot.

src/test/java : Contient les tests unitaires, notamment pour le contrôleur StudentController.

Configuration
Base de données MySQL :
Le fichier application.properties dans le dossier src/main/resources permet de configurer la connexion à la base de données MySQL.
Avant de démarrer l'application, il est nécessaire de créer la base de données studentdb et de configurer correctement l'URL de connexion, le nom d'utilisateur et le mot de passe dans ce fichier.

Annotations Spring :
L'annotation @Repository appliquée sur StudentRepository permet de gérer les exceptions liées aux opérations sur la base de données.

Exécution du Projet
Créez la base de données MySQL studentdb si ce n'est pas déjà fait.
Configurez la connexion à la base de données dans le fichier application.properties.
Lancez l'application avec la commande Maven suivante :
bash
mvn spring-boot:run
Une fois l'application démarrée, vous pouvez accéder à l'interface Swagger UI pour tester l'API à l'adresse suivante :
http://localhost:8080/swagger-ui.html

video Démo : https://github.com/user-attachments/assets/cf49dbbb-b963-44f6-8f92-18b78b60fce9

