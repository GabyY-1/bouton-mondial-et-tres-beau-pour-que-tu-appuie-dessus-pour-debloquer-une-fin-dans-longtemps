# Le Bouton Mondial 🔴

Un bouton. Une mission inutile. Interface plein écran et icônes Lucide.

## Démarrage
Ouvrir `index.html` ou activer GitHub Pages sur la branche `main` (racine). Aucun build nécessaire.

## Synchronisation avec Supabase
Projet Supabase : `rtxtwbizfbsjhvttyatn`. Les tables et fonctions serveur ont été créées directement dans ce projet :
- `button_world` : total mondial permanent.
- `button_players` : pseudo et clics par compte (total, semaine et jour UTC).
- `button_click()` : incrément atomique du joueur et du total mondial ; limitation de fréquence basique (150 ms).
- `button_set_pseudo(text)` : changement du pseudo du compte.
- Row Level Security activée ; seuls les appels RPC authentifiés peuvent écrire des clics.
- Supabase Realtime + rafraîchissement de secours toutes les 15 secondes.

## Règle de contribution
Les comptes connectés contribuent au **compteur mondial**. Les visiteurs non connectés peuvent cliquer, mais leurs clics sont **locaux et provisoires** et ne sont pas encore transférés automatiquement lors de l'inscription. Ils n'apparaissent pas dans les classements mondiaux.

Un clic de compte connecté nécessite une réponse positive du serveur. Les clics trop rapprochés ne sont pas comptabilisés. Aucun multiplicateur.

## Important
La confirmation e-mail est un paramètre à ajuster manuellement dans Supabase Auth > Providers > Email : la présence de ce formulaire ne désactive pas elle-même cette confirmation.

Les classements sont récupérés depuis le serveur (jusqu'à 1000 profils). Le site ne prétend pas afficher des utilisateurs fictifs. Les succès mondiaux et le grand événement final restent à implémenter ; l'interface présente leur préparation.
