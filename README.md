# 🚴‍♂️ Cycling Classics Calendar Automator

Ce projet permet d'automatiser l'ajout des classiques cyclistes (Ardennaises, Flandriennes, etc.) dans **Google Calendar** directement depuis un fichier **Google Sheets**.

L'objectif est d'avoir un rappel précis pour ne pas rater le début des retransmissions TV.

## ✨ Fonctionnalités

- **Importation automatisée** : Ajoute les courses dans l'agenda via un script Google Apps Script.
- **Idempotence** : Le script vérifie la colonne "Statut" pour éviter de créer des doublons si on le relance.
- **Rappels personnalisés** : Crée un événement de 30 minutes avec une notification immédiate à l'heure définie.
- **Gestion simplifiée** : Pas besoin de gérer le format complexe des événements "Toute la journée" de Google.

## 📊 Structure du Google Sheets

Le script attend un tableau avec la structure suivante :

| Colonne A | Colonne B | Colonne C | Colonne D |
| :--- | :--- | :--- | :--- |
| **Nom de la course** | **Date** (JJ/MM/AAAA) | **Heure** (HH:mm) | **Statut Import** |
| Paris-Roubaix | 12/04/2026 | 13:00 | |

## 🚀 Installation et Utilisation

1. Créez un nouveau **Google Sheets** avec les colonnes ci-dessus.
2. Allez dans `Extensions` > `Apps Script`.
3. Copiez le code contenu dans `code.js` de ce dépôt et collez-le dans l'éditeur.
4. Enregistrez et cliquez sur le bouton **Exécuter** (une autorisation sera demandée lors du premier lancement).
5. (Optionnel) Créez un bouton dans votre feuille de calcul (Insertion > Dessin) et liez-le à la fonction `ajouterCourseAvecHeureSpecifique`.

## ⚙️ Configuration du Script

Le script est actuellement configuré pour :
- Une durée d'événement de **30 minutes**.
- Un rappel **0 minute avant** (au moment du début de l'heure saisie).
- Une vérification sur la **colonne D** pour marquer l'importation.

---
Projet créé par un passionné de cyclisme pour ne plus jamais rater une attaque dans le Vieux Quaremont ! 🏁
