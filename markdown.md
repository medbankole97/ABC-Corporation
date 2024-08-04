 Conception d'une base de données pour centraliser et automatiser les opérations commerciales d'ABC Corporation.

    ##  Organisation du Projet
     Après avoir analysé les ressources fournies, le projet a été organisé et planifié sur Trello. Les tâches ont été décomposées comme suit :

	1-Téléchargement et analyse des ressources
	2- Réalisation du dictionnaire de données
            - Création d'un document détaillant les entités et leurs attributs.
            - Outils utilisés : Google Sheets.
	3- Conception du Modèle Conceptuel de Données (MCD)
            - Utilisation d'un outil de modélisation pour concevoir le MCD.
            - Outils utilisés : Looping.
	4- Transformation du MCD en Modèle Logique de Données (MLD)
            
	5- Création d'un fichier SQL contenant les scripts pour créer la base de données et les tables
            - Écriture des scripts SQL pour créer la base de données et les tables.
            - Outils utilisés : MySQL ( en mode console ).

## Instructions d'Installation

### Étapes d'Installation

```créarion de la base de données
CREATE DATABASE order_management;
```

```utiliser la bdd
USE order_management;
```

```table customers
CREATE TABLE customers (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    address VARCHAR(50) NOT NULL,
    email VARCHAR(50) NOT NULL UNIQUE,
    phone VARCHAR(30) NOT NULL UNIQUE
);
```
```table products
CREATE TABLE products (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    description VARCHAR(100) NOT NULL,
    price DECIMAL(10,2) NOT NULL,
    stock INT NOT NULL
);
```
```table purchase_orders
CREATE TABLE purchase_orders (
    id INT AUTO_INCREMENT PRIMARY KEY,
    order_date DATE NOT NULL,
    delivery_address VARCHAR(50) NOT NULL,
    customer_id INT NOT NULL,
    FOREIGN KEY (customer_id) REFERENCES customers(id)
);
```
```table order_details
CREATE TABLE order_details (
    id INT AUTO_INCREMENT PRIMARY KEY,
    quantity INT NOT NULL,
    price DECIMAL(10,2) NOT NULL,
    order_id INT NOT NULL,
    product_id INT NOT NULL,
    FOREIGN KEY (order_id) REFERENCES purchase_orders(id),
    FOREIGN KEY (product_id) REFERENCES products(id)
);
```
[Lien pour en savoir plus sur le fichier README.md](README.md)