# Luma — votre budget personnel en francs congolais

## Ouvrir votre gestionnaire

Ouvrez **Luma.html** dans un navigateur récent (Edge, Chrome ou Firefox). Tout est inclus dans ce fichier : aucune installation, aucun abonnement, aucune connexion nécessaire pour la version locale.

Luma commence avec un jeu de démonstration clairement signalé. Cliquez sur **Créer mon budget** pour démarrer votre propre budget vide en CDF. Aucune donnée de démonstration n’est copiée dans votre budget réel.

## Les premiers pas

1. Ajoutez vos comptes : compte bancaire, Mobile Money, espèces et épargne.
2. Renseignez le solde de chaque compte avant les premières opérations saisies ou importées. Si vous partez d’aujourd’hui sans historique, c’est votre solde actuel. Si vous importez un relevé ancien, utilisez le solde avant sa première ligne.
3. Ajoutez revenus et dépenses. Saisissez un retrait d’espèces comme un **virement**, pour ne pas compter deux fois votre argent.
4. Créez quelques enveloppes mensuelles et les récurrences importantes.
5. Fixez vos projets d’épargne. Les sommes réservées restent dans vos comptes mais sont déduites de la marge disponible.
6. Exportez régulièrement une copie complète dans les paramètres.

## Ce que vous pouvez faire

- Vue d’ensemble : soldes, revenus, dépenses, différence du mois et comparaison à période comparable.
- Graphiques de flux mensuels et répartition des dépenses par catégorie.
- Comptes multiples, virements neutres, rapprochement du solde constaté.
- Ajout, modification et suppression d’opérations ; notes, filtres, recherche, pagination et opérations futures.
- Enveloppes par catégorie, montant restant, dépassements et report mensuel optionnel.
- Projets d’épargne, échéance, réserve, libération d’une réserve et repère mensuel pour atteindre la cible.
- Dépenses et revenus récurrents : mensuels, hebdomadaires et annuels ; mise en pause ; enregistrement d’une occurrence sans création automatique de doublons.
- Dettes et sommes prêtées : suivi du montant restant, mensualités et remboursements liés aux opérations.
- Projection de trésorerie à 30, 60 et 90 jours et calendrier d’échéances.
- Simulateur « Et si… » : achat envisagé, baisse des revenus futurs, réduction des dépenses variables, comparaison avec la situation actuelle.
- Points d’attention calculés à partir des données, sans prétendre à une prédiction parfaite.
- Import CSV avec choix des colonnes, aperçu et détection des doublons.
- Export CSV des opérations et sauvegarde/restauration JSON de toutes les données.
- Rapport imprimable, mode discret à l’écran et catégories personnelles.
- Bouton d’annulation temporaire après une modification.

## Sauvegarde locale : à savoir

Dans **Luma.html**, les données sont conservées dans le stockage IndexedDB du navigateur, sur cet appareil. Elles ne sont pas synchronisées entre appareils et ne sont pas chiffrées par un mot de passe Luma. Évitez le mode de navigation privée pour conserver le budget après fermeture. Effacer les données du navigateur peut effacer ce budget.

**Exportez une copie JSON régulièrement et avant de changer de navigateur ou d’appareil.** Importez ensuite cette copie dans l’autre navigateur pour retrouver le budget. Le fichier HTML ne contient pas vos finances : elles restent dans le navigateur ; exporter le budget est donc nécessaire pour les déplacer.

Le mode discret masque les montants à l’écran : ce n’est pas un verrou de sécurité.

## Lire les prévisions

Les prévisions partent du solde actuel, moins les réserves des projets. Elles ajoutent les opérations futures et les récurrences, retirent les mensualités, puis estiment les dépenses variables à partir des 30 derniers jours. Les échéances de dépense et mensualités du mois déjà passées mais non enregistrées sont imputées aujourd’hui ; les revenus échus non reçus ne sont pas considérés comme encaissés.

Les dépenses reconnues comme des récurrences ou remboursements ne sont pas réintégrées dans le rythme variable. Associez une charge déjà payée à sa récurrence si nécessaire. Le résultat dépend de l’exhaustivité des saisies et des revenus effectivement reçus.

Une récurrence enregistrée représente une échéance réglée, même si son montant réel diffère de l’estimation. Pour un prêt, les paiements partiels sont suivis séparément et déduits de la mensualité prévue.

Le simulateur ne modifie jamais les comptes. Il ne déplace pas d’argent et ne réalise aucun achat.

## Importer un CSV

L’en-tête doit identifier les colonnes. Les séparateurs virgule, point-virgule et tabulation sont acceptés ; les champs entre guillemets sont reconnus. Les dates peuvent être au format `AAAA-MM-JJ` ou `JJ/MM/AAAA`. Les nombres français comme `1 250 000` et `1.234,56` sont acceptés.

Sélectionnez le compte concerné, la date, le libellé, le montant et, si elles existent, les colonnes type et catégorie. Pour un relevé à montants signés, les montants négatifs sont les dépenses. Confirmez l’aperçu avant l’import. Les opérations identiques (date, type, montant, compte et libellé) sont proposées comme doublons ignorés ; deux dépenses réellement identiques peuvent donc devoir être ajoutées manuellement.

Les virements exigent deux comptes et se saisissent séparément. Le CSV est un journal d’opérations ; pour déplacer **tout** le budget sans perdre les relations, utilisez la sauvegarde JSON.

## Version privée en ligne

Le dossier contient aussi le code d’une version hébergée avec authentification Sites et base D1 par propriétaire. Sa mise en ligne n’a pas pu être terminée dans cet environnement : l’accès réseau au dépôt source est bloqué. Aucun lien de production n’est donc présenté comme disponible. La version locale reste utilisable sans ce service.

## Vérifications et limites

23 tests automatisés vérifient notamment les virements, les échéances, les prévisions, les réserves, les reports, les paiements partiels, les formats CSV, la validation serveur, l’isolation des propriétaires et les conflits de sauvegarde.

Le contrôle interactif dans le navigateur n’a pas pu être effectué : l’aperçu local est inaccessible depuis l’environnement et l’ouverture d’un fichier local par l’outil de navigateur est interdite. Les fichiers JavaScript et la version autonome ont été contrôlés syntaxiquement ; il ne faut pas confondre ces contrôles avec un essai visuel complet.

Pas de connexion bancaire automatique, de conversion de change en direct, de déclaration fiscale, ni de calcul d’intérêts de prêt. La devise est verrouillée après les premières opérations pour éviter de relabeller des montants sans conversion. La version actuelle accepte jusqu’à 8 000 opérations par budget. Les données sont exprimées en centimes entiers pour éviter les erreurs de calcul usuelles ; l’affichage CDF est arrondi au franc.

