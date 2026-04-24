---
version: alpha
name: Audela
description: A glass-material interface anchored by a full-bleed grid and a violet-to-cyan gradient signature.
colors:
  primary: "#49E1F8"
  secondary: "#961EE1"
  tertiary: "#4989F8"
  neutral: "#FFFFFF"
  background: "#FFFFFF"
  surface: "#EAEAEA"
  text-primary: "#565656"
  text-secondary: "#272727"
  border: "#EAEAEA"
  accent: "#49E1F8"
typography:
  display-lg:
    fontFamily: Roboto
    fontSize: 72px
    fontWeight: 400
    lineHeight: 72px
    letterSpacing: "-0.025em"
  body-md:
    fontFamily: Roboto
    fontSize: 18px
    fontWeight: 300
    lineHeight: 29.25px
  label-md:
    fontFamily: Roboto
    fontSize: 14px
    fontWeight: 400
    lineHeight: 20px
rounded:
  sm: 4px
  md: 12px
  lg: 24px
  full: 9999px
spacing:
  xs: 2px
  sm: 4px
  md: 8px
  lg: 12px
  xl: 16px
  "2xl": 24px
  "3xl": 32px
components:
  button-primary:
    backgroundColor: "{colors.secondary}"
    textColor: "{colors.neutral}"
    typography: "{typography.label-md}"
    rounded: "{rounded.md}"
    padding: 10px
  button-secondary:
    backgroundColor: "{colors.neutral}"
    textColor: "{colors.text-secondary}"
    typography: "{typography.label-md}"
    rounded: "{rounded.md}"
    padding: 10px
  button-link:
    textColor: "{colors.text-primary}"
    typography: "{typography.label-md}"
    rounded: "{rounded.sm}"
    padding: 0px
  card:
    backgroundColor: "{colors.neutral}"
    rounded: "{rounded.md}"
    padding: 24px
  input:
    backgroundColor: "{colors.neutral}"
    textColor: "{colors.text-primary}"
    rounded: "{rounded.sm}"
    padding: 10px
---

## Overview

A glass-material interface anchored by a full-bleed grid and a violet-to-cyan gradient signature. The aesthetic is retro-futurist and technical — generous breathing room, strong structural framing, and translucent surfaces layered over a subtle dot-matrix background. The mood is precise and meditative without being cold. Expressive motion and premium gradient edges signal polish; a single Roboto family across the stack keeps the voice neutral and engineered.

## Colors

The palette pairs a cyan primary with a violet secondary, joined in a signature gradient that carries the brand. Neutrals stay warm and minimal so glass surfaces read cleanly.

- **Primary (#49E1F8):** Cyan accent for emphasis, focus rings, and active states.
- **Secondary (#961EE1):** Violet supporting accent and origin of the signature gradient.
- **Tertiary (#4989F8):** Blue reserved for supporting contrast moments.
- **Neutral (#FFFFFF):** Foundation for backgrounds, surfaces, and supporting chrome.
- **Background (#FFFFFF):** Page background, pure white.
- **Surface (#EAEAEA):** Cards, panels, and recessive surfaces.
- **Text Primary (#565656):** Body text, descriptions, default label color.
- **Text Secondary (#272727):** Headings and high-emphasis labels.
- **Border (#EAEAEA):** Card borders, dividers, input borders — subtle and recessive.
- **Accent (#49E1F8):** Focus rings, highlighted borders, interactive states.

The signature gradient runs linear from secondary to primary (`#961EE1` → `#49E1F8`) and is reserved for primary buttons, the logo, and the gradient border shell treatment described under Elevation.

## Typography

Typography runs on a single Roboto family across display, body, and utility text, letting weight and scale carry hierarchy instead of multiple families. This choice keeps the voice engineered and technical — not editorial.

- **Display (`display-lg`):** Roboto Regular (400) at 72px with tight letter spacing (-0.025em). Used for hero headlines.
- **Body (`body-md`):** Roboto Light (300) at 18px with a comfortable 29.25px line-height. Used for long-form reading.
- **Label (`label-md`):** Roboto Regular (400) at 14px. Used for buttons, nav, and UI chrome.

Roboto must be loaded from Google Fonts with weights 300 and 400. Do not substitute Inter, system-ui, or any other humanist sans — the geometric neutrality of Roboto is intentional.

## Layout

The page is a full-bleed grid. Keep that structural frame stable before remixing ornament or component styling. The 4px base rhythm drives every padding, margin, and gap; larger values step up from that cadence rather than introducing unrelated numbers.

- **Layout type:** Grid, full bleed
- **Base unit:** 4px
- **Scale:** 2, 4, 8, 12, 16, 24, 32px
- **Section padding:** 24px
- **Card padding:** 24px
- **Component gaps:** 8, 12, 16, 24px

## Elevation & Depth

Surfaces read as glass first. Borders, shadows, and blur reinforce that material — they don't replace it. Keep these recipes consistent across hero panels, cards, and controls so the page reads as one material system.

- **Surface style:** Glass (translucent with backdrop-blur)
- **Borders:** 1px `#EAEAEA` on resting surfaces; 1px `#49E1F8` on focused or accented surfaces; 2px `#FFFFFF` inset highlight on elevated glass
- **Shadows:** Resting card uses `rgba(255,255,255,0.8) 0 1px 1px 0 inset, rgba(39,39,39,0.05) 0 25px 50px -12px`. Accented hero surfaces can layer a violet glow `rgba(150,30,225,0.3) 0 10px 20px -5px`.
- **Blur:** 24px for nav and overlays, 32px for hero glass panels

The signature depth technique is the **gradient border shell**: wrap a key surface in an outer shell with 24px padding and a 12px radius, drive the shell with `linear-gradient(to right, #961EE1, #49E1F8)`, and inset the real content surface inside with a slightly smaller radius. The gradient reads as a hairline premium frame, never a flat stroke.

## Shapes

Radii anchor at 4px and scale up in a controlled family. Larger surfaces can open up to 24px, but controls and badges stay within the same rounded DNA — no sharper exceptions, no pill-only detours outside the defined 9999px avatars and status dots.

- **Corner radii:** 4px (inputs, tight surfaces), 12px (buttons, cards, gradient shells), 24px (hero panels), 9999px (avatars, status dots)
- **Icon treatment:** Linear
- **Icon set:** Solar

## Components

- **Buttons — Primary:** Violet-to-cyan gradient background, white text, 12px radius, 10px padding, `label-md` typography. One per view section.
- **Buttons — Secondary:** White background, dark text (`text-secondary`), 12px radius, 10px padding.
- **Buttons — Link:** Transparent background, `text-primary` color, no radius, no padding. Used for inline navigation and tertiary actions.
- **Cards:** Glass surface with 1px border, 12px radius, 24px internal padding. Hero cards wrap in the gradient border shell with an inset white highlight.
- **Inputs:** 1px `#EAEAEA` border, white background, 4px radius, 10px padding, 14px font. Focus state: border turns accent cyan.
- **Navigation:** Full-bleed bar with 24px backdrop-blur reinforcing the glass material. Structural grid frame remains visible across sections.
- **Background layer:** Full-bleed WebGL dot-matrix particle field with slow breathing pulse and subtle pointer-reactive drift. DOM fallback preserved for reduced-motion and non-WebGL contexts.

Motion timing clusters around 150ms for micro-interactions, 500ms for section transitions, 100ms for fast hover feedback, and 2000ms for ambient background motion. Easing favors `ease`, `ease-in-out`, and `cubic-bezier(0.4, 0, 1, 0.2)`. Hover patterns rely on text color, transform, grayscale, opacity, and shadow shifts. Scroll choreography uses parallax for section reveals.

## Do's and Don'ts

- Do use cyan (#49E1F8) as the main accent for emphasis and interactive states.
- Do reserve the violet-to-cyan gradient for primary buttons, the logo, and the gradient border shell.
- Do treat every surface as glass first — borders, shadows, and blur reinforce that material.
- Do maintain the 4px spacing grid for all padding, margins, and gaps.
- Do keep corner radii within the 4px, 12px, 24px, 9999px family.
- Do load Roboto weights 300 and 400 from Google Fonts before rendering.
- Don't substitute Inter, system-ui, or any other sans for Roboto — the geometric neutrality is intentional.
- Don't introduce extra accent colors outside the core palette unless a new semantic state requires it.
- Don't mix unrelated shadow or blur recipes that break the glass depth system.
- Don't apply the signature gradient to static decoration — it belongs on primary surfaces and the logo only.
- Don't invent sharper or pill-only exceptions for controls and badges.
- Don't place more than one primary (gradient-filled) button in the same view section.
