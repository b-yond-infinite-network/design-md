# Conventions — Non-Normative Extensions

The [`DESIGN.md` alpha spec](https://github.com/google-labs-code/design.md/blob/main/docs/spec.md) does not yet cover assets or theme modes. The spec explicitly allows unknown top-level YAML keys and unknown `##` sections (they are preserved, not errored). This file documents the conventions we use in this repo so agents and humans can interpret them consistently.

## 1. Theme modes — separate files

Each brand has:

- `DESIGN.md` — light theme (the default, and the canonical file).
- `DESIGN.dark.md` — dark theme. Same `name:`, same semantic token names (`surface`, `on-surface`, `primary`, etc.), different hex values.

Both files declare identical component entries so a consumer can swap one palette for the other without changing component references.

Reserved future suffixes (not used yet): `DESIGN.highcontrast.md`, `DESIGN.marketing.md`.

## 2. Assets — colocated folder + `assets:` YAML block

Assets live in `companies/<company>/assets/` (or `companies/<company>/products/<product>/assets/` for product brands) and are referenced by a non-normative `assets:` block in the YAML front matter:

```yaml
assets:
  logo: ./assets/logo.svg
  logo-dark: ./assets/logo-dark.svg
  wordmark: ./assets/wordmark.svg
  favicon: ./assets/favicon.svg
  social-card: ./assets/social-card.png
```

Prefer SVG for logos and wordmarks. Only check in binaries (PNG/JPG) when SVG is not viable (e.g., social preview cards).

A human-readable `## Assets` section in the prose body describes how each asset should be used.

## 3. Icons — `icons:` YAML block

```yaml
icons:
  library: lucide       # "lucide" | "phosphor" | "material-symbols" | "custom"
  path: ./assets/icons  # only if library is "custom"
  size-sm: 16px
  size-md: 20px
  size-lg: 24px
  stroke: 1.5px         # for outline-style libraries
```

A human-readable `## Iconography` section describes style (outline vs filled), weight, and metaphor conventions.

## 4. Component naming

- Use semantic, hyphen-cased names: `button-primary`, `input-default`, `card`, `nav-item`.
- Variants use a suffix: `-hover`, `-active`, `-disabled`, `-pressed`.
- Prefer token references (`{colors.primary}`) over literal hex inside `components:` — this is what makes the light/dark file swap work cleanly.

## 5. Forward-compatibility notes

- When the spec formalizes a `modes:` block (tracked informally), we will migrate from separate files to a single file with a `modes.dark` section. The semantic token names we use today map 1:1 so migration is mechanical.
- When the spec adds native `icons.*` tokens (see [issue #41](https://github.com/google-labs-code/design.md/issues/41)), we will migrate our `icons:` block to the official shape.
- When the spec adds OKLCH support ([issue #27](https://github.com/google-labs-code/design.md/issues/27)), we may re-author palettes in OKLCH. Until then, SRGB hex only.
