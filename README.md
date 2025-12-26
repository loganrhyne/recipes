# Recipes

This repo is a personal cookbook designed for **ChatGPT-first capture and retrieval**.

- Paste a URL, image, or raw recipe text into ChatGPT.
- ChatGPT extracts *only* the recipe and relevant notes/tips.
- Recipes are stored as **structured Markdown** using a consistent schema (v1) so they can be parsed later.

---

## Schema v1 (Structured Markdown)

Each recipe lives in a single Markdown file with:

1. **YAML frontmatter** for metadata
2. **Required sections** with fixed headings

The goal is:

- Human-readable recipes
- Predictable structure for future parsing
- No scripts required — ChatGPT + GitHub UI is sufficient

---

## File layout & naming

Preferred:

- `recipes/<slug>.md`

Optional subfolders (purely organizational):

- `recipes/mains/<slug>.md`
- `recipes/sides/<slug>.md`
- `recipes/soups-stews/<slug>.md`
- `recipes/salads/<slug>.md`
- `recipes/breakfast/<slug>.md`
- `recipes/snacks/<slug>.md`
- `recipes/desserts/<slug>.md`
- `recipes/baking/<slug>.md`
- `recipes/drinks/<slug>.md`
- `recipes/sauces-condiments/<slug>.md`
- `recipes/weeknight/<slug>.md`
- `recipes/meal-prep/<slug>.md`
- `recipes/dietary/vegetarian/<slug>.md`
- `recipes/dietary/vegan/<slug>.md`
- `recipes/dietary/gluten-free/<slug>.md`
- `recipes/dietary/dairy-free/<slug>.md`
- `recipes/uncategorized/<slug>.md`

Slug rules:

- lowercase
- hyphen-separated
- no dates or source names unless needed

Examples:

- `apple-pie.md`
- `eggplant-curry.md`

---

## Frontmatter

### Required fields

```yaml
---
title: "Apple Pie"
source_url: "https://example.com/apple-pie"
added: "2025-12-26"   # YYYY-MM-DD
---
```

### Strongly recommended (when known)

```yaml
author: "Little Spoon Farm"
yield: "1 (9-inch) pie"

time:
  prep: "20 min"
  cook: "55 min"
  total: "3 hr 20 min"

tags: [dessert, pie, apples]
```

### Optional fields

```yaml
cuisine: "American"
methods: [bake]
equipment: ["9-inch deep-dish pie plate"]
notes: "Brief high-level note that belongs above the recipe body."
```

### Metadata rules

- Omit fields if unknown — do not guess
- Prefer **strings** for times and yield
- Keep `source_url` as the canonical origin

---

## Required sections

Use these headings **exactly**:

- `## Ingredients`
- `## Instructions`

Recommended (include only if meaningful):

- `## Notes & Tips`
- `## Storage`
- `## Variations`

---

## Section formatting rules

### Ingredients

- Bullet list only
- Keep wording close to the source
- Put prep inline (e.g. `2 apples, peeled and sliced`)

### Instructions

- Numbered list (`1.`, `2.`, ...)
- Preserve temperatures, timings, and doneness cues

### Notes & Tips

- Only include actionable technique or quality tips
- Avoid blog or narrative content

### Storage

- Refrigeration, freezing, and reheating instructions if present

---

## Template

See: `templates/recipe.template.md`
