# Recipe Content Repository

This directory contains all recipe and ingredient data for the Recipes app.

## Structure

```
content/
├── recipes/
│   ├── index.json                 # Recipe listing (metadata for all recipes)
│   ├── dal-tadka/
│   │   └── index.json             # Full recipe data
│   ├── palak-paneer/
│   │   └── index.json
│   ├── masala-dosa/
│   │   └── index.json
│   ├── chole-bhature/
│   │   └── index.json
│   ├── biryani/
│   │   └── index.json
│   └── butter-chicken/
│       └── index.json
└── ingredients/
    ├── turmeric/
    │   └── index.json             # Full ingredient data
    ├── toor-dal/
    │   └── index.json
    └── [other ingredients...]
```

## Files

### `recipes/index.json`
List of all recipes with metadata used for:
- Recipe listing page
- Search and filter
- Recipe cards display

**Key fields:**
- `slug` — URL-friendly identifier
- `title` — Display name
- `description` — Short summary
- `cuisines`, `dietaryTags`, `healthTags` — For filtering
- `difficulty` — easy, medium, hard
- `prepTime`, `cookTime` — in minutes
- `defaultServings` — default serving size
- `featured`, `popular` — Boolean flags for homepage sections
- `dataUrl` — Link to full recipe details

### `recipes/[slug]/index.json`
Full recipe data including:
- Detailed description
- Hero image URL
- **Variants** — Recipe variations (spicy, quick, dietary modifications)
- **Ingredients** — Detailed ingredient list with amounts, units, notes
- **Steps** — Cooking instructions with sub-steps and tips
- **SEO** — Meta title and description

### `ingredients/[slug]/index.json`
Comprehensive ingredient data:
- **names** — Multilingual ingredient names (6 Indian languages)
- **photoUrl** — Ingredient photo
- **description** — What it is and how it's used
- **flavorProfile** — Taste description
- **nutritionalProperties** — Per 100g nutritional info
- **medicinalProperties** — Health benefits with sources
- **commonSubstitutes** — Alternative ingredients
- **storageTips** — How to store properly
- **buyingTips** — What to look for when buying

## Data Format

All files are JSON with consistent schemas defined in the app's TypeScript types:
- `src/types/recipe.ts` — Recipe types
- `src/types/ingredient.ts` — Ingredient types

## Recipes Included

1. **Dal Tadka** — Creamy yellow lentils with tempering
2. **Palak Paneer** — Spinach curry with cottage cheese
3. **Masala Dosa** — Crispy crepe with spiced potato
4. **Chole Bhature** — Chickpea curry with fried bread
5. **Hyderabadi Biryani** — Layered rice with meat
6. **Butter Chicken** — Creamy tomato-butter curry

## Ingredients Included

1. **Turmeric** — Golden spice with anti-inflammatory properties
2. **Toor Dal** — Yellow lentils, staple protein source

## Adding New Content

To add a new recipe:
1. Create `recipes/[new-slug]/index.json` with full recipe details
2. Add entry to `recipes/index.json` with metadata
3. Reference any new ingredients in the recipe
4. Update ingredient files if new ingredients are used

To add a new ingredient:
1. Create `ingredients/[new-slug]/index.json`
2. Follow the schema with multilingual names
3. Include nutritional and medicinal properties
4. Reference in relevant recipes

## Deployment

This content is served from GitHub as raw JSON. The app fetches from:
```
https://raw.githubusercontent.com/Roopesht/recipecontent/main/content/
```

Configure the base URL via the `NEXT_PUBLIC_CONTENT_BASE_URL` environment variable in the main app.
