# 📧 ÉTAPE 1 DÉTAILLÉE : Configuration EmailJS pour l'envoi automatique d'emails

## 🎯 Objectif
Configurer EmailJS pour recevoir automatiquement un email à `jadetaraf@hotmail.fr` à chaque fois qu'une commande est validée sur le site.

---

## ⏱️ Temps estimé : 15-20 minutes

---

## 📝 PARTIE A : Créer un compte EmailJS

### A1. Inscription
1. Ouvrez votre navigateur web (Chrome, Firefox, Edge...)
2. Allez sur **https://www.emailjs.com/**
3. En haut à droite, cliquez sur **"Sign Up"** (S'inscrire)
4. Vous avez 2 options :
   - **Option A** : S'inscrire avec Google (recommandé - plus rapide)
     - Cliquez sur "Continue with Google"
     - Choisissez votre compte Gmail
     - Acceptez les permissions
   
   - **Option B** : S'inscrire avec email
     - Entrez votre adresse email
     - Choisissez un mot de passe
     - Cliquez sur "Sign Up"
     - Allez dans votre boîte mail
     - Cliquez sur le lien de confirmation

5. Une fois connecté, vous arrivez sur le **Dashboard** (tableau de bord)

---

## 📬 PARTIE B : Créer un Service Email

### B1. Accéder aux Services
1. Dans le menu de gauche du Dashboard, cliquez sur **"Email Services"**
2. Vous verrez une page vide avec un bouton **"Add New Service"**
3. Cliquez sur **"Add New Service"**

### B2. Choisir Gmail (Recommandé)
1. Une popup s'ouvre avec plusieurs options :
   - Gmail ⭐ (Recommandé)
   - Outlook/Hotmail
   - Yahoo
   - Custom SMTP
   
2. Cliquez sur **"Gmail"**

### B3. Connecter votre compte Gmail
1. Donnez un nom à votre service (ex: "Boulangerie_PEI")
2. Cliquez sur **"Connect Account"**
3. Une fenêtre Google s'ouvre
4. Choisissez le compte Gmail que vous voulez utiliser pour ENVOYER les emails
   - ⚠️ Important : Ce compte enverra les emails à jadetaraf@hotmail.fr
   - Vous pouvez utiliser n'importe quel compte Gmail
5. Google vous demandera d'autoriser EmailJS :
   - Cliquez sur **"Autoriser"** ou **"Allow"**
6. Vous revenez sur EmailJS

### B4. Finaliser le Service
1. Vous voyez maintenant votre service créé
2. **IMPORTANT** : Notez le **Service ID** (exemple: `service_abc1234`)
   - Il apparaît sous le nom de votre service
   - Copiez-le quelque part (bloc-notes, fichier texte...)
   - Format : `service_xxxxxxx`

📝 **Service ID à noter :** `_____service_j6gjv9k__________________`

---

## 📄 PARTIE C : Créer un Template Email (Modèle)

### C1. Accéder aux Templates
1. Dans le menu de gauche, cliquez sur **"Email Templates"**
2. Cliquez sur **"Create New Template"**

### C2. Configuration de base
Vous voyez un formulaire avec plusieurs champs :

#### Champ 1 : Template Name (Nom du modèle)
- Entrez : **"Nouvelle_Commande_Boulangerie"**

#### Champ 2 : From Name (Nom de l'expéditeur)
- Entrez : **"Menu Boulangerie PEI"**
- C'est le nom qui apparaîtra comme expéditeur de l'email

#### Champ 3 : From Email
- Laissez tel quel (votre Gmail automatique)

#### Champ 4 : Subject (Objet de l'email)
- Entrez exactement : **`Nouvelle Commande #{{order_number}} - Boulangerie PEI`**
- ⚠️ Ne modifiez pas les `{{order_number}}` - c'est une variable

#### Champ 5 : To Email (Destinataire) ⚠️ IMPORTANT
- Entrez directement : **`jadetaraf@hotmail.fr`**
- ⚠️ **NE PAS** mettre de `{{ }}` ni de variables
- ⚠️ **Tapez directement l'adresse email complète**
- C'est l'adresse qui recevra TOUTES les commandes

### C3. Contenu de l'email (Body)
Dans la grande zone de texte "Content", **EFFACEZ TOUT** et copiez-collez exactement ceci :

```
🥖 BOULANGERIE PEI - NOUVELLE COMMANDE 🥗
════════════════════════════════════════════════

📋 COMMANDE N° {{order_number}}
Date : {{date}} à {{time}}

════════════════════════════════════════════════

👤 INFORMATIONS CLIENT
────────────────────────────────────────────────
Nom         : {{client_prenom}} {{client_nom}}
Téléphone   : {{client_telephone}}

════════════════════════════════════════════════

🍽️ DÉTAILS DE LA COMMANDE
────────────────────────────────────────────────
Formule     : {{formule}}

Plat        : {{plat}}

Dessert     : {{dessert}}

Boisson     : {{boisson}}

════════════════════════════════════════════════

💰 MONTANT TOTAL : {{total}} €

════════════════════════════════════════════════

⏰ Action requise : Préparer cette commande
📞 Contacter le client si nécessaire au {{client_telephone}}

────────────────────────────────────────────────
Email automatique - Ne pas répondre
Système de commande en ligne - Boulangerie PEI
```

### C4. Sauvegarder le Template
1. En haut à droite, cliquez sur **"Save"** (Sauvegarder)
2. **IMPORTANT** : Notez le **Template ID**
   - Il apparaît en haut de la page
   - Format : `template_xxxxxxx`
   - Copiez-le quelque part

📝 **Template ID à noter :** `____template_05z813q___________________`

### C5. Tester le Template (Optionnel mais recommandé)
1. Cliquez sur **"Test It"** en haut à droite
2. Remplissez les champs de test :
   - `to_email` : jadetaraf@hotmail.fr
   - `order_number` : 000001
   - `date` : 08/01/2026
   - `time` : 12:30
   - `client_nom` : DUPONT
   - `client_prenom` : Jean
   - `client_telephone` : 06 12 34 56 78
   - `formule` : 🥪 Menu Sandwich
   - `plat` : Poulet Mayonnaise
   - `dessert` : Brownie Chocolat
   - `boisson` : Coca Cola
   - `total` : 9.10
3. Cliquez sur **"Send Test Email"**
4. Vérifiez votre boîte `jadetaraf@hotmail.fr`
   - ⚠️ Regardez aussi dans les SPAMS/COURRIER INDÉSIRABLE
5. Si vous recevez l'email, c'est parfait ! ✅

---

## 🔑 PARTIE D : Obtenir la clé publique (Public Key)

### D1. Accéder aux paramètres du compte
1. En haut à droite, cliquez sur votre nom/avatar
2. Dans le menu déroulant, cliquez sur **"Account"**
3. Ou bien, dans le menu de gauche, cliquez sur **"Account"** puis **"General"**

### D2. Trouver la Public Key
1. Vous voyez une section **"API Keys"**
2. Cherchez la ligne **"Public Key"**
3. Vous verrez une clé de format : `user_xxxxxxxxxxxx`
4. Cliquez sur l'icône 📋 (copier) à côté
5. Ou sélectionnez et copiez manuellement

📝 **Public Key à noter :** `_______________________`

---

## 💻 PARTIE E : Mettre à jour le fichier HTML

Maintenant que vous avez vos 3 clés, il faut les mettre dans le code.

### E1. Ouvrir le fichier
1. Ouvrez le fichier **MenuBoulangeriePEI_v2.html** avec un éditeur de texte :
   - Bloc-notes (Windows)
   - Notepad++
   - Visual Studio Code
   - Ou clic droit > "Modifier" ou "Edit"

### E2. Remplacer YOUR_PUBLIC_KEY
1. Utilisez la fonction "Rechercher" (Ctrl+F)
2. Cherchez : `YOUR_PUBLIC_KEY`
3. Vous devriez trouver cette ligne (ligne ~11) :
```javascript
emailjs.init("YOUR_PUBLIC_KEY");
```
4. Remplacez `YOUR_PUBLIC_KEY` par votre Public Key (gardez les guillemets)
5. Exemple :
```javascript
emailjs.init("user_abc123def456");
```

### E3. Remplacer YOUR_SERVICE_ID
1. Cherchez : `YOUR_SERVICE_ID`
2. Vous devriez trouver cette ligne (ligne ~889) :
```javascript
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams)
```
3. Remplacez `YOUR_SERVICE_ID` par votre Service ID (gardez les apostrophes)
4. Exemple :
```javascript
emailjs.send('service_abc1234', 'YOUR_TEMPLATE_ID', templateParams)
```

### E4. Remplacer YOUR_TEMPLATE_ID
1. Sur la même ligne, remplacez `YOUR_TEMPLATE_ID` par votre Template ID
2. Exemple final :
```javascript
emailjs.send('service_abc1234', 'template_xyz7890', templateParams)
```

### E5. Sauvegarder le fichier
1. Appuyez sur Ctrl+S ou cliquez sur "Fichier" > "Enregistrer"
2. ✅ Le fichier est maintenant configuré !

---

## ✅ VÉRIFICATION FINALE

### Checklist
- [ ] J'ai créé un compte EmailJS
- [ ] J'ai créé un Service Gmail et noté le Service ID
- [ ] J'ai créé un Template et noté le Template ID
- [ ] J'ai copié ma Public Key
- [ ] J'ai remplacé les 3 valeurs dans le fichier HTML :
  - `YOUR_PUBLIC_KEY` → `user_xxxxxxxxx`
  - `YOUR_SERVICE_ID` → `service_xxxxxxx`
  - `YOUR_TEMPLATE_ID` → `template_xxxxxxx`
- [ ] J'ai sauvegardé le fichier

---

## 🧪 TEST AVANT MISE EN LIGNE

Vous pouvez tester localement :

1. Double-cliquez sur le fichier **MenuBoulangeriePEI_v2.html**
2. Il s'ouvre dans votre navigateur
3. Remplissez le formulaire de commande
4. Validez jusqu'au bout
5. Vérifiez votre boîte `jadetaraf@hotmail.fr`
   - ⚠️ Regardez dans les SPAMS si vous ne voyez rien
6. Si vous recevez l'email : **BRAVO ! Ça fonctionne !** 🎉

---

## 🚨 PROBLÈMES COURANTS

### Problème 1 : Erreur 422 "The recipients address is corrupted" ⚠️
**C'est le problème le plus fréquent !**

**Cause :** Le champ "To Email" dans votre template EmailJS est mal configuré

**Solution (2 méthodes) :**

**Méthode A - SIMPLE (Recommandée) :**
1. Allez dans EmailJS > Email Templates
2. Cliquez sur votre template "Nouvelle_Commande_Boulangerie"
3. Dans le champ **"To Email"**, supprimez tout
4. Tapez directement : `jadetaraf@hotmail.fr`
5. Ne mettez PAS de `{{ }}` ni de variables
6. Cliquez sur "Save"
7. Testez à nouveau

**Méthode B - Avec variable (Plus complexe) :**
Si vous voulez garder `{{to_email}}`, il faut :
1. Dans EmailJS, allez dans "Settings" de votre template
2. Cochez "Allow custom recipients"
3. Ajoutez `{{to_email}}` dans la whitelist
4. Sauvegardez

**✅ Après correction :** Testez immédiatement avec le "Test It" dans EmailJS

---

### Problème 2 : "EmailJS is not defined"
**Solution :** Vérifiez que vous avez bien une connexion internet (le script EmailJS doit se charger)

### Problème 3 : Je ne reçois pas d'email
**Solutions :**
1. Vérifiez vos SPAMS/Courrier indésirable dans jadetaraf@hotmail.fr
2. Vérifiez que les 3 IDs sont corrects dans le code
3. Vérifiez dans la console du navigateur (F12) s'il y a des erreurs
4. Testez avec le "Test It" dans EmailJS pour voir si ça fonctionne
5. Si le "Test It" fonctionne mais pas le site, revérifiez les IDs dans le HTML

### Problème 4 : Erreur "Invalid public key"
**Solution :** Revérifiez que vous avez bien copié la Public Key complète (`user_xxxxx`)

### Problème 5 : Erreur 403 ou 401
**Solution :** 
1. Allez dans EmailJS > Account > General
2. Vérifiez que votre compte est bien vérifié (email confirmé)
3. Dans "Allowed Origins", ajoutez `*` pour autoriser tous les domaines (temporairement pour tester)

### Problème 6 : "Service ID is invalid"
**Solution :** 
1. Retournez dans EmailJS > Email Services
2. Vérifiez le Service ID exact (cliquez sur votre service pour le voir)
3. Copiez-le à nouveau et remplacez dans le HTML

---

## 📊 LIMITES DU PLAN GRATUIT

- **200 emails par mois** (largement suffisant !)
- Si vous dépassez, vous recevrez un email d'avertissement
- Pas de carte bancaire requise
- Parfait pour une petite boulangerie

---

## 🎓 RÉCAPITULATIF DES 3 CLÉS

Notez-les ici pour référence :

```
Public Key (user_xxxxx)     : _______________________

Service ID (service_xxxxx)  : _______________________

Template ID (template_xxxxx): _______________________
```

---

## ➡️ ÉTAPE SUIVANTE

Une fois cette étape terminée, passez à l'**ÉTAPE 2** du fichier `GUIDE_MISE_EN_LIGNE.md` pour mettre le site en ligne sur GitHub Pages, Netlify ou Vercel.

---

**Besoin d'aide ?** 
- Documentation EmailJS : https://www.emailjs.com/docs/
- Vidéos tutoriels : YouTube "EmailJS tutorial"

**Bon courage ! Vous y êtes presque ! 🚀**
