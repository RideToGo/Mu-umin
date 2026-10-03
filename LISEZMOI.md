# Site de l'association Mu-umin des pays des Grands Lacs

Site statique (un seul fichier `index.html`) en français, anglais, swahili et arabe.

## Publier sur Render

1. Créez un dépôt GitHub (par exemple `mu-umin-site`) et envoyez-y le contenu de ce dossier.
2. Sur https://dashboard.render.com, cliquez **New > Blueprint**, choisissez le dépôt.
   Render lit `render.yaml` et crée le site statique `mu-umin-grands-lacs` (gratuit).
3. Le site est en ligne à l'adresse `https://mu-umin-grands-lacs.onrender.com`.
   Dans **Settings > Custom Domains**, vous pouvez ajouter `mu-umin.ca`.

Chaque envoi sur GitHub redéploie automatiquement le site.

## Fichiers à ajouter

- `adhan.mp3` : l'enregistrement de l'adhan joué à l'heure de la prière.
  Sans ce fichier, un carillon doux est joué à la place.
- `releves/AAAA-MM.pdf` : le relevé bancaire officiel de chaque mois.

## Ajouter le relevé du mois (trésorière)

Dans `index.html`, cherchez `releves:` et ajoutez une ligne :

    {mois:"2026-10",extra:[{date:"2026-10-31",k:"fees",montant:-12.5}],pdf:"releves/2026-10.pdf"},

Les contributions et dépenses du mois sont reprises automatiquement.

## Important avant la mise en service réelle

Cette version garde les comptes et les données dans le navigateur de chaque visiteur.
Pour protéger réellement l'espace membres (liste des membres, relevés bancaires),
il faut ajouter un service d'authentification et une base de données (par exemple
Supabase), ainsi que Stripe ou Square pour les cartes et Twilio pour les textos et WhatsApp.
