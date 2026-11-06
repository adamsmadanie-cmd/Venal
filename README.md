# 🗞️ VÉNAL — Plateforme Médias & Presse

> **"INFORMATIONS C'EST ICI"**

VÉNAL est une application web moderne et épurée (HTML5, CSS3, JavaScript ES6+ Modulaire) conçue pour les journalistes, éditeurs et professionnels de l'information. La plateforme permet la création et l'édition de profil professionnel complet, la publication d'articles enrichis avec images, et l'interaction directe au sein d'un fil d'actualités synchronisé en temps réel sur **Android, iOS et Web**.

---

## 🎨 Style & Design System

- **Direction Artistique** : Épuré "Blanc Éditorial" avec boutons Noir Profond.
- **Accents Visuels** : Logo 3D CSS, bordures animées 2D (effet *Scanner Light Frame*).
- **Mobile-First** : Interface entièrement responsive, adaptée aux écrans tactiles et smartphones.

---

## 🚀 Fonctionnalités Principales

### 1. Authentification & Profils Professionnels (Firebase Auth & Firestore)
- Inscription et connexion sécurisées via email/mot de passe.
- Édition complète du profil professionnel :
  - Nom complet ou pseudonyme
  - Organisme de presse / Média
  - Numéro de Carte de Presse
  - Photo de profil (URL)
  - Bio & Domaine d'expertise

### 2. Studio de Rédaction & Fil d'Actualités en Temps Réel
- Publication d'articles avec titre, image de couverture et corps du texte.
- Distribution instantanée des dépêches sur le fil public grâce à la réactivité en temps réel de Firestore.
- Badges de presse et affichage des médias d'affiliation des auteurs.

---

## 🛠️ Architecture & Technologies

- **Frontend** : HTML5 sémantique, CSS3 (variables, backdrop-blur, animations 2D/3D), JavaScript ES6+ Modulaire.
- **Backend / Cloud** : Firebase v13 SDK Modulaire (`firebase-auth`, `firebase-firestore`).
- **Hébergement** : Compatible GitHub Pages, Vercel ou n'importe quel hébergeur web statique.

---

## 📁 Structure du Projet

```text
venal-press-app/
├── index.html        # Application complète (HTML, CSS & JS Modulaire Firebase)
└── README.md         # Documentation du projet
