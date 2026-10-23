# Luma — budget personnel en CDF

Application autonome : comptes, revenus, dépenses, enveloppes, projets, dettes, récurrences, graphiques et projections. Aucun serveur ni installation de dépendances requis.

## Publication GitHub Pages

1. Déposez les fichiers de ce dossier à la racine du dépôt `LUMA` (le fichier `index.html` doit être à la racine).
2. Dans GitHub, ouvrez **Settings → Pages**.
3. Choisissez **Deploy from a branch**, puis la branche **main** et le dossier **/(root)**. Enregistrez.
4. Attendez le déploiement et ouvrez le lien indiqué par GitHub Pages sur votre téléphone.

Un compte GitHub Free demande un dépôt public pour GitHub Pages. Documentation : https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

## Vos données personnelles

Le site et son code sont publics. Les opérations saisies sont enregistrées dans IndexedDB, dans le navigateur utilisé, sur l'appareil utilisé. L'application n'envoie pas ces opérations à GitHub et n'offre pas de synchronisation entre appareils ni de connexion bancaire.

Vous pouvez saisir vos vrais montants, revenus, dépenses et soldes dans **Créer mon budget**. Les prévisions sont des estimations. La version actuelle ne chiffre pas vos données et ne protège pas leur accès par un mot de passe Luma. Le bouton de confidentialité masque uniquement l'affichage. Une personne ayant accès à votre navigateur peut accéder au budget.

Ne saisissez pas de codes PIN, mots de passe bancaires ou numéros complets de carte. Exportez régulièrement une sauvegarde JSON et conservez-la dans un endroit privé. Ne publiez jamais ces sauvegardes ni de relevés bancaires dans le dépôt GitHub. Effacer les données du navigateur peut effacer le budget ; évitez la navigation privée.

Pour passer du PC au mobile, exportez la sauvegarde complète depuis les paramètres puis importez-la sur le téléphone. Les changements ultérieurs ne seront pas synchronisés. Une restauration remplace le budget courant : sauvegardez-le d'abord. Le budget de l'ancien fichier local ne sera pas automatiquement transféré au site en ligne.

## État de cette livraison

Application publiée dans le dépôt dokiasi15-lgtm/LUMA. L'activation GitHub Pages reste à effectuer dans Settings → Pages ; aucun site en ligne n'est confirmé à ce stade. Le fichier index.html reprend la version autonome existante, sans y inclure les données enregistrées dans votre navigateur. Voir Guide_Luma.md pour les fonctionnalités et leurs limites.

