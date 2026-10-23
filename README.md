# withings-callback

Page statique servant de `redirect_uri` OAuth2 pour l'API Withings, publiée sur GitHub Pages.
Elle affiche les paramètres `code` et `state` reçus dans l'adresse ; elle n'envoie rien, ne stocke rien et ne charge aucun script externe.

## URL à enregistrer sur developer.withings.com

```
https://kazeg.github.io/withings-callback/
```

À saisir caractère pour caractère, slash final compris (Withings compare l'URL exactement).

## Modifier la page

1. Éditer `index.html`.
2. Si le contenu du `<script>` change, recalculer son empreinte et la reporter dans la balise `Content-Security-Policy` (`script-src 'sha256-…'`) ; le workflow échoue et affiche l'empreinte attendue si elle ne correspond pas.
3. Commit puis push sur `main` : le workflow `.github/workflows/pages.yml` déploie la page et vérifie par une requête HEAD qu'elle répond 200.

Aucun secret n'a sa place ici : ni `client_id`, ni `client_secret`, ni jeton.
