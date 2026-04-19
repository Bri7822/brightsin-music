# Design System Strategy: The Cinematic Nocturne

## 1. Overview & Creative North Star
**The Creative North Star: "The Sonic Void"**
This design system is built to evoke the immersive, high-fidelity experience of a premium midnight performance. We are moving away from the "grid-of-boxes" web standard toward a high-end editorial experience. The system treats the screen as a dark stage where light and depth are created through tonal layering rather than structural lines. 

By leveraging intentional asymmetry—such as overlapping typography and offset imagery—we break the "template" look. This creates a rhythmic flow that mirrors the artist's music: unpredictable, polished, and deeply atmospheric.

## 2. Colors & Surface Philosophy
The palette is rooted in deep obsidian and charcoal, providing a high-contrast stage for the electric violet accents.

*   **The "No-Line" Rule:** To maintain a premium, seamless feel, 1px solid borders are strictly prohibited for sectioning. Separation of content must be achieved through background color shifts. For example, a `surface-container-low` section should sit directly against a `surface` background to define its boundary.
*   **Surface Hierarchy & Nesting:** Depth is physical. Use the surface-container tiers to "lift" elements toward the user:
    *   **Base:** `surface` (#0e0e0e) for the primary background.
    *   **Secondary Zones:** `surface-container-low` (#131313) for large content areas.
    *   **Interactive Cards:** `surface-container-high` (#201f1f) or `surface-container-highest` (#262626) to make elements pop against the base.
*   **The "Glass & Gradient" Rule:** Navigation bars and music players must utilize the Glassmorphism effect. Use `surface` at 60% opacity with a `24px` backdrop-blur to create a "frosted" look. 
*   **Signature Textures:** For high-impact CTAs, use a linear gradient transitioning from `primary` (#db90ff) to `primary-container` (#d37bff) at a 135-degree angle. This adds a subtle "glow" that flat colors cannot replicate.

## 3. Typography
The typography strategy pairs the technical precision of **Space Grotesk** with the humanistic clarity of **Manrope**.

*   **Display & Headlines (Space Grotesk):** Used for "Brand Moments." These should be bold, high-contrast, and occasionally use negative letter-spacing (-2%) for a tighter, more editorial feel.
*   **Body & Labels (Manrope):** Used for data-heavy sections like tracklists and bios. Manrope's geometric yet friendly nature ensures readability against dark backgrounds.
*   **Editorial Overlap:** Encourage `display-lg` text to partially overlap cover art or secondary containers. This breaks the "container" feel and adds professional depth.

## 4. Elevation & Depth
In this design system, light is the primary architect. We use Tonal Layering instead of traditional shadows.

*   **The Layering Principle:** To create a card effect, place a `surface-container-highest` element on top of a `surface` background. The subtle shift in grey creates a sophisticated "lift."
*   **Ambient Shadows:** If a floating element (like a modal) requires a shadow, it must be massive and soft. Use a blur of `40px` to `60px` with an opacity of `8%`, using a tinted shadow derived from `primary_dim` to simulate the glow of the accent color.
*   **The "Ghost Border" Fallback:** If a boundary is absolutely necessary for accessibility, use the `outline-variant` token at 15% opacity. Never use 100% opaque borders.
*   **Glassmorphism Depth:** The music player and navigation should feel like they are floating above the content. Use the `surface-container` tokens with transparency and backdrop-blur to ensure the "Artist Imagery" flows beneath the UI as the user scrolls.

## 5. Components

### Buttons
*   **Primary:** Solid `primary` (#db90ff) with `on-primary` text. Use `full` roundedness (capsule shape).
*   **Secondary:** Ghost style. No background, `outline` token at 20% for the border, with `primary` text.
*   **Hover State:** Primary buttons should scale slightly (102%) and increase their "glow" (inner shadow of `surface-tint`).

### Cards (Album Art & Events)
*   **Styling:** Use `xl` (1.5rem) rounded corners for album art. 
*   **Interaction:** On hover, the image should subtly scale up within its container (overflow: hidden), and the `surface-container` background should shift from `low` to `highest`.
*   **No Dividers:** Never use lines to separate tracks in a list. Use `title-md` for the track name and `body-sm` for the duration, separated by vertical whitespace (`1.5rem`).

### The Global Player
*   **Surface:** Semi-transparent `surface-container-lowest` with a heavy backdrop blur.
*   **Accent:** The progress bar must use the `primary` (#db90ff) color with a subtle drop shadow of the same color to create a "neon wire" effect.

### Selection Chips
*   **State:** Unselected chips use `surface-variant`. Selected chips use the `primary` background with `on-primary` text.

## 6. Do's and Don'ts

### Do
*   **DO** use extreme scale. A `display-lg` headline next to a `body-sm` label creates a premium, high-contrast hierarchy.
*   **DO** use "breathable" whitespace. Allow elements to have significant padding (use the `xl` or `lg` spacing values) to prevent the dark theme from feeling cramped.
*   **DO** ensure all interactive icons have a `48x48px` touch target, even if the visual icon is smaller.

### Don't
*   **DON'T** use pure #000000 for everything. Use the `surface` and `surface-container` tokens to create a sense of three-dimensional space.
*   **DON'T** use standard 1px dividers. They look "cheap" and break the cinematic immersion. Use tonal shifts instead.
*   **DON'T** use high-saturation colors for body text. Always use `on-surface` (#ffffff) or `on-surface-variant` (#adaaaa) to ensure eye comfort in dark mode.