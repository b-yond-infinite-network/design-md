# B-Yond Family — DESIGN.md

This repository holds [`DESIGN.md`](https://github.com/google-labs-code/design.md) visual-identity specifications for the B-Yond family of brands. Each file describes one brand's design system in a form that coding agents can read and apply.

## Brand family

| Entity    | Type                | Relationship      | Path                                      |
| --------- | ------------------- | ----------------- | ----------------------------------------- |
| B-Yond    | Company (parent)    | —                 | `companies/byond/`                        |
| Agility   | Product             | Product of B-Yond | `companies/byond/products/agility/`       |
| Telco     | Product             | Product of B-Yond | `companies/byond/products/telco/`         |
| Audela    | Company (services)  | Independent       | `companies/audela/`                       |

B-Yond products (Agility, Telco) share typographic and layout DNA with the parent B-Yond brand but carry their own accent/primary colors. Audela has an independent identity and does not inherit from B-Yond.

## Repository layout

```
companies/
  <company>/
    DESIGN.md              # corporate brand (light)
    DESIGN.dark.md         # corporate brand (dark), optional
    assets/                # logos, wordmarks, favicons, icons
    README.md              # company blurb + links
    products/              # only for companies that have products
      <product>/
        DESIGN.md          # product brand (light)
        DESIGN.dark.md     # product brand (dark), optional
        assets/
        README.md
CONVENTIONS.md             # documents our non-normative extensions
```

## How agents should consume this

1. Pick the entity: `companies/<company>/` for a corporate brand, or `companies/<company>/products/<product>/` for a product brand.
2. Read `DESIGN.md` for the default (light) theme.
3. If dark mode is needed, read `DESIGN.dark.md` — it defines the same semantic token names with dark-appropriate values.
4. Consult `assets/` for logo, wordmark, favicon, and icon sources referenced in the `assets:` YAML block and `## Assets` prose.
5. Consult `CONVENTIONS.md` for the meaning of non-normative keys (`assets:`, `icons:`, `## Assets`, `## Iconography`).

## Local tooling

```bash
npm install
npm run lint          # lints every DESIGN*.md under brands/
npm run lint:byond    # lint just the parent brand
```

CI runs `npm run lint` on every push (see `.github/workflows/lint.yml`).

## Status

Alpha. Token values are placeholders pending real brand colors, type, and assets from each brand team.
