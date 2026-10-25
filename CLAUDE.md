# withings-callback — page de retour OAuth2 Withings (GitHub Pages, dépôt public)

Page statique : reçoit `code` et `state` dans l'adresse et les renvoie à l'application Android Morning Widget. Détail et mode d'emploi : `README.md`.

## Règles
- Dépôt public : aucun secret, aucun identifiant (`client_id`, `client_secret`), aucun jeton, aucune donnée personnelle, ni dans les fichiers ni dans les messages de commit.
- `index.html` n'envoie rien à un serveur, ne stocke rien et ne charge aucun script externe. Ne pas relâcher la politique `Content-Security-Policy`.
- Si le contenu du `<script>` change, recalculer son empreinte `sha256` et la reporter dans la balise CSP : le workflow échoue et affiche l'empreinte attendue sinon.
- L'URL de retour enregistrée chez Withings se compare caractère pour caractère : ne pas renommer le dépôt ni changer le chemin.
- Pousser sur `main` déploie la page : seulement avec l'accord de Kamel, après relecture du diff.
- Ne pas modifier `.claude/` ni `.github/` sans l'accord de Kamel.
