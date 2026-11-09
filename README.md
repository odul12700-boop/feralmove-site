# feralmove-site

Site de **FeralMove** (feralmove.com) : une page d'accueil, la politique de
confidentialité (`/privacy/`, ouverte par l'app) et les mentions légales.
Jekyll, sur le gabarit et la charte de feralsync.com. Aucun cookie, aucun
traceur, aucune ressource externe.

Construit par la séance S24 du dépôt `feralmove` (ticket `docs/seances/S24.md`).

## Mise en ligne (à faire par Ludo, une seule fois)

**Dans cet ordre** : le domaine se déclare dans GitHub **avant** de toucher au
DNS, pour que personne d'autre ne puisse le réclamer entre-temps.

### 1. GitHub (ce dépôt)

1. **Settings** → **Pages** (menu de gauche).
2. Source : **Deploy from a branch** → branche `main`, dossier `/ (root)` →
   **Save**.
3. **Custom domain** : `feralmove.com` (normalement déjà rempli grâce au
   fichier `CNAME`) → **Save**.

### 2. Gandi — domaine feralmove.com, enregistrements DNS

1. Supprimer les enregistrements de parking : `@` A `217.70.184.38` et `www`
   CNAME `webredir…`.
2. Ajouter quatre enregistrements A sur `@` :
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`.
3. Ajouter `www` en CNAME vers `odul12700-boop.github.io.` (avec le point
   final).
4. Ne rien toucher d'autre (MX éventuels compris).

### 3. Retour sur GitHub

Attendre que le contrôle DNS passe au vert (de quelques minutes à quelques
heures), puis cocher **Enforce HTTPS**. S'il reste bloqué : **Remove**, puis
ressaisir le domaine et **Save** (même astuce que pour feralsync.com).

### 4. feralmove.fr

Chez Gandi, **redirection web permanente (301)** de `feralmove.fr` vers
`https://feralmove.com`. Ici, **garder** les enregistrements de parking du
`.fr` : ce sont eux qui font la redirection.

## Après la publication de l'app

Remplacer le badge « Bientôt sur Google Play » de `index.md` par le lien vers la
fiche Play Store (comme sur feralsync.com).
