# Working Culture

Jeu d'affrontement entre deux équipes sur le thème de la culture au travail, sous forme de page web statique. À chaque tour, une équipe fait tourner la roulette, tombe sur une catégorie et doit réaliser le défi associé. La première équipe à **5 points** remporte la partie.

Tout tient dans un seul fichier, `working_culture.html` (HTML, CSS et JavaScript), sans serveur, sans dépendance et sans installation.

## Règles du jeu

1. Deux équipes s'affrontent. L'Équipe 1 commence.
2. L'équipe dont c'est le tour clique sur **Tourner la roulette**.
3. La roulette s'arrête sur une catégorie et un défi de cette catégorie s'affiche.
4. L'équipe tente de réaliser le défi (mime, quiz, improvisation, discussion…).
5. L'animateur ou l'équipe adverse valide le résultat :
   - **Défi relevé** : l'équipe marque 1 point.
   - **Défi raté** : aucun point.
6. La main passe à l'autre équipe.
7. La première équipe qui atteint **5 points** gagne. Un message de victoire s'affiche avec le score final, et il est possible de rejouer.

Un même défi ne revient pas tant que tous les défis de sa catégorie n'ont pas été tirés.

## Les catégories

La roulette contient 8 catégories, avec 5 défis chacune (40 défis au total) :

- Communication
- Esprit d'équipe
- Management
- Créativité
- Culture d'entreprise
- Vie pro / perso
- Bureau & Télétravail
- Culture générale pro

## Lancer le jeu

Ouvre `working_culture.html` dans un navigateur récent (Chrome, Firefox, Safari, Edge) en double-cliquant dessus.

La page s'adapte aux écrans de téléphone et suit le thème clair ou sombre du navigateur. La police est chargée depuis Google Fonts ; sans connexion, une police système prend le relais.

## Mettre le jeu en ligne

Le fichier est autonome : dépose-le tel quel sur un hébergeur statique (GitHub Pages, Netlify, Vercel, etc.).

- Renomme-le `index.html` pour qu'il s'ouvre directement à la racine du site.
- Sur GitHub Pages : crée un dépôt, ajoute `index.html`, puis active Pages dans *Settings > Pages* en choisissant la branche principale.
- Sur Netlify : glisse-dépose le dossier contenant le fichier sur la page *Sites*.

## Personnaliser le jeu

Tout se règle dans la balise `<script>` du fichier HTML.

### Changer les défis ou les catégories

Modifie le tableau `CATEGORIES`. Chaque entrée contient :

```js
{
  nom: "Communication",
  couleur: "#d64533",
  defis: [
    "Premier défi...",
    "Deuxième défi..."
  ]
}
```

Tu peux ajouter ou retirer des catégories : la roulette se redessine automatiquement avec le bon nombre de segments. Choisis des couleurs assez foncées pour que le texte blanc reste lisible.

### Changer le nombre de points pour gagner

Modifie la constante `POINTS_POUR_GAGNER` (valeur par défaut : `5`). Le texte « Première équipe à N points » se met à jour tout seul.

### Changer l'apparence

Les couleurs, les polices et le thème clair/sombre sont définis par des variables CSS (`--bg`, `--surface`, `--accent`, `--team1`, `--team2`…) au début de la balise `<style>`. Modifier ces variables suffit à changer toute l'identité visuelle.

La taille de la roulette se règle avec la constante `TAILLE` dans le script (440 par défaut) et la propriété `max-width` du `canvas` dans le CSS.

## Structure du projet

```
.
├── working_culture.html   # le jeu (HTML + CSS + JS)
└── README.md
```

## Idées d'évolution

- Ajouter un chronomètre pour les défis chronométrés.
- Gérer plus de deux équipes.
- Ajouter une catégorie « joker » ou des points bonus.
- Enregistrer l'historique des parties dans le navigateur.
