# HomeMaid — carnet de recettes

## Installation sur GitHub Pages
1. Déposez les quatre fichiers `index.html`, `manifest.webmanifest`, `sw.js` et `recettes-exemple.json` à la racine de votre dépôt GitHub.
2. Dans **Settings → Pages**, choisissez la branche et le dossier `/ (root)`.
3. Ouvrez l'adresse publiée sur votre téléphone puis utilisez **Ajouter à l'écran d'accueil** dans le navigateur.

## Fonctions
- Création, modification, suppression et recherche de recettes.
- Catégories, appareils (Cookeo, Air fryer, four…), favoris et tri.
- Ajustement du nombre de personnes et recalcul des quantités ; conversion automatique g → kg et ml → L.
- Import d'un fichier JSON ou collage du JSON préparé par ChatGPT.
- Export de sauvegarde JSON et impression / PDF.
- Interface responsive et installation PWA avec cache de base.

## Données et sauvegarde
Les recettes sont enregistrées dans le stockage local du navigateur (`localStorage`). GitHub Pages ne permet pas à la page web d'écrire dans le dépôt. Les recettes ne se synchronisent donc pas automatiquement entre appareils : utilisez **Exporter** puis **Importer JSON** sur l'autre appareil. Conservez régulièrement une copie de `homemaid-recettes.json`.

## Format JSON pour ChatGPT
```json
{
  "app": "HomeMaid",
  "version": 1,
  "recipes": [{
    "title": "Nom de la recette", "category": "Plat", "device": "Cookeo",
    "servings": 4, "prepTime": 10, "cookTime": 20,
    "ingredients": [{"name": "Pommes de terre", "amount": 600, "unit": "g"}],
    "steps": ["Première étape", "Deuxième étape"]
  }]
}
```
L'import accepte aussi un objet recette seul, un tableau de recettes, et les alias `name`, `qty`, `prep`, `cook` et `instructions`.
