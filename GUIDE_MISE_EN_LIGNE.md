# 🌐 Guide de Mise en Ligne du Menu Boulangerie PEI

## 📧 ÉTAPE 1 : Configuration de l'envoi d'emails (EmailJS)

### 1.1 Créer un compte EmailJS (Gratuit)
1. Allez sur **https://www.emailjs.com/**
2. Cliquez sur "Sign Up" pour créer un compte gratuit
3. Confirmez votre email

### 1.2 Créer un Service Email
1. Dans le dashboard EmailJS, allez dans **"Email Services"**
2. Cliquez sur **"Add New Service"**
3. Choisissez votre fournisseur d'email (Gmail recommandé)
4. Suivez les instructions pour connecter votre compte email
5. Notez votre **SERVICE_ID** (ex: service_abc123)

### 1.3 Créer un Template Email
1. Allez dans **"Email Templates"**
2. Cliquez sur **"Create New Template"**
3. Configurez le template avec :
   - **To Email** : `{{to_email}}`
   - **Subject** : `Nouvelle Commande #{{order_number}} - Boulangerie PEI`
   - **Content** (exemple) :
   ```
   Nouvelle commande reçue !
   
   📋 DÉTAILS DE LA COMMANDE
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   N° de commande : {{order_number}}
   Date : {{date}}
   Heure : {{time}}
   
   👤 CLIENT
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   Nom : {{client_nom}}
   Prénom : {{client_prenom}}
   Téléphone : {{client_telephone}}
   
   🍽️ COMMANDE
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   Formule : {{formule}}
   Plat : {{plat}}
   Dessert : {{dessert}}
   Boisson : {{boisson}}
   
   💰 TOTAL : {{total}}€
   
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   Boulangerie PEI
   ```
4. Sauvegardez et notez votre **TEMPLATE_ID** (ex: template_xyz789)

### 1.4 Obtenir votre clé publique
1. Allez dans **"Account"** > **"General"**
2. Copiez votre **Public Key** (ex: user_abcdef123456)

### 1.5 Mettre à jour le fichier HTML
Dans le fichier **MenuBoulangeriePEI_v2.html**, remplacez :
- `YOUR_PUBLIC_KEY` (ligne ~8) par votre Public Key
- `YOUR_SERVICE_ID` (ligne ~889) par votre Service ID
- `YOUR_TEMPLATE_ID` (ligne ~889) par votre Template ID

**Exemple :**
```javascript
emailjs.init("user_abcdef123456");
...
emailjs.send('service_abc123', 'template_xyz789', templateParams)
```

---

## 🌐 ÉTAPE 2 : Mettre le site en ligne (GRATUIT)

### Option A : GitHub Pages (Recommandé - Le plus simple)

#### Prérequis
- Créer un compte GitHub : https://github.com/

#### Instructions
1. **Créer un nouveau repository**
   - Connectez-vous à GitHub
   - Cliquez sur "New repository"
   - Nom : `menu-boulangerie-pei`
   - Cochez "Public"
   - Cliquez sur "Create repository"

2. **Télécharger GitHub Desktop** (optionnel mais plus simple)
   - Téléchargez : https://desktop.github.com/
   - Installez et connectez-vous avec votre compte GitHub

3. **Publier votre fichier**
   
   **Via GitHub Desktop :**
   - Clonez votre repository
   - Copiez le fichier `MenuBoulangeriePEI_v2.html` dans le dossier
   - Renommez-le en `index.html` (important !)
   - Commit et Push les changements
   
   **Via le site web GitHub :**
   - Allez dans votre repository
   - Cliquez sur "Add file" > "Upload files"
   - Glissez-déposez `MenuBoulangeriePEI_v2.html`
   - Renommez-le en `index.html`
   - Cliquez sur "Commit changes"

4. **Activer GitHub Pages**
   - Dans votre repository, allez dans "Settings"
   - Dans le menu de gauche, cliquez sur "Pages"
   - Sous "Source", sélectionnez "main" branch
   - Cliquez sur "Save"
   - Attendez 2-3 minutes

5. **Votre site est en ligne !**
   - URL : `https://VOTRE_USERNAME.github.io/menu-boulangerie-pei/`
   - Partagez ce lien à qui vous voulez !

---

### Option B : Netlify (Très simple aussi)

1. Allez sur **https://www.netlify.com/**
2. Créez un compte gratuit
3. Cliquez sur "Add new site" > "Deploy manually"
4. Glissez-déposez votre dossier contenant `MenuBoulangeriePEI_v2.html`
   (Renommez le fichier en `index.html` d'abord)
5. Netlify vous donnera une URL type : `random-name-123.netlify.app`
6. Vous pouvez personnaliser le nom dans les paramètres

---

### Option C : Vercel

1. Allez sur **https://vercel.com/**
2. Créez un compte gratuit
3. Cliquez sur "Add New" > "Project"
4. Importez depuis GitHub ou uploadez votre fichier
5. Déployez !

---

## 🔗 Partager le lien

Une fois en ligne, vous obtenez une URL permanente comme :
- `https://votre-username.github.io/menu-boulangerie-pei/`
- `https://menu-boulangerie.netlify.app/`

**Toute personne avec ce lien pourra :**
- ✅ Accéder au site de commande
- ✅ Passer une commande
- ✅ Recevoir un ticket de caisse
- ✅ Vous envoyer automatiquement un email récapitulatif

---

## 📱 Bonus : Créer un QR Code

Pour faciliter l'accès depuis un mobile :

1. Allez sur **https://www.qr-code-generator.com/**
2. Collez votre URL
3. Téléchargez le QR Code
4. Imprimez-le et affichez-le dans votre boulangerie !

---

## 🔧 Maintenance

### Mettre à jour le site
- **GitHub Pages** : Modifiez le fichier sur GitHub ou via GitHub Desktop
- **Netlify/Vercel** : Réuploadez le fichier ou connectez à GitHub pour auto-déploiement

### Vérifier les emails reçus
- Connectez-vous à votre boîte mail jadetaraf@hotmail.fr
- Vous recevrez un email pour chaque commande validée

---

## ❓ Support

### Problèmes courants

**Les emails ne sont pas envoyés ?**
- Vérifiez que vous avez bien remplacé les 3 IDs dans le code
- Vérifiez votre quota EmailJS (100 emails/mois gratuits)
- Regardez la console du navigateur (F12) pour les erreurs

**Le site ne s'affiche pas ?**
- Vérifiez que le fichier s'appelle bien `index.html`
- Attendez quelques minutes après la publication
- Videz le cache de votre navigateur (Ctrl+F5)

**Besoin d'aide ?**
- GitHub Pages : https://docs.github.com/pages
- EmailJS : https://www.emailjs.com/docs/
- Netlify : https://docs.netlify.com/

---

## 📊 Limites gratuites

- **EmailJS** : 200 emails/mois gratuits
- **GitHub Pages** : Illimité
- **Netlify** : 100 GB bande passante/mois
- **Vercel** : 100 GB bande passante/mois

Ces limites sont largement suffisantes pour une boulangerie ! 🥖

---

**Bonne mise en ligne ! 🚀**
