# Design System Document: Sultan Alfaro Portfolio

## 1. Overview & Creative North Star: "The Obsidian Curator"

This design system is built to transcend the standard "developer portfolio" template. The Creative North Star is **The Obsidian Curator**—a philosophy that treats digital space like a high-end, darkened gallery where work is illuminated by soft, atmospheric light rather than harsh structural lines.

The goal is to move away from rigid, boxy layouts toward a fluid, editorial experience. We achieve this through:
*   **Intentional Asymmetry:** Breaking the 12-column grid with staggered content blocks to create a sense of rhythm and discovery.
*   **Atmospheric Depth:** Using "Glassmorphism" and tonal layering to create a UI that feels like it’s floating in a deep, midnight ether.
*   **High-Contrast Scale:** Utilizing extreme shifts between `display-lg` typography and `label-sm` metadata to establish an authoritative, editorial hierarchy.

---

## 2. Colors

The palette is rooted in deep obsidian tones, punctuated by high-vibrancy accents that suggest energy and precision.

### Core Palette (Material Convention)
*   **Background:** `#131318` (The canvas)
*   **Surface:** `#131318` (Primary interface level)
*   **Primary (Violet-Blue):** `#c4c0ff` (Main interactive elements)
*   **Secondary (Teal):** `#41eec2` (Success states/Secondary highlights)
*   **On-Surface:** `#e4e1e9` (Standard text)
*   **Surface-Container-Low:** `#1b1b20` (Subtle sectioning)
*   **Surface-Container-Highest:** `#35343a` (Elevated interactive cards)

### The "No-Line" Rule
Traditional 1px solid borders are strictly prohibited for sectioning. Structural boundaries must be achieved through **background color shifts**. For example, a project gallery section should transition from `background` to `surface-container-low` to define its start, rather than using a divider line.

### Glass & Gradient Implementation
To achieve "The Obsidian Curator" look, use `surface_tint` (Violet-Blue) as a very low-opacity (2-5%) radial gradient in the background of hero sections. This provides a visual "soul" that flat hex codes cannot replicate.

---

## 3. Typography

The system utilizes a dual-font strategy to balance character with readability.

*   **Display & Headlines (Plus Jakarta Sans):** Chosen for its geometric precision and modern flair. Use `display-lg` for hero statements with a negative letter-spacing of `-0.02em` to create a "tight," premium editorial feel.
*   **Body & UI (Inter):** The workhorse font. Inter provides maximum legibility at small sizes (`body-sm`) and ensures the UI feels functional and accessible.

**Hierarchy Guidance:**
*   **Display (3.5rem):** Reserved for name and primary value propositions.
*   **Headline (2rem - 1.5rem):** Used for section titles.
*   **Title (1.125rem):** Used for card titles and prominent links.
*   **Body (1rem):** Standard reading text.

---

## 4. Elevation & Depth

We eschew traditional shadows in favor of **Tonal Layering** and **Glassmorphism**.

### The Layering Principle
Hierarchy is defined by stacking surface tiers. 
1.  **Level 0:** `surface_container_lowest` (Background)
2.  **Level 1:** `surface_container_low` (In-page sections)
3.  **Level 2:** `surface_container_high` (Interactive cards/modals)

### Ambient Shadows
When an element must "float" (like a dropdown or a CTA button), use a shadow that mimics natural light. 
*   **Shadow:** `0px 24px 48px -12px rgba(0, 0, 0, 0.5)`
*   **Tint:** Incorporate a 4% `primary` color tint into the shadow to make it feel integrated with the dark theme.

### The "Ghost Border" & Glass
For accessibility on cards, use the "Ghost Border": a 1px stroke using `outline_variant` at **15% opacity**. 
*   **Glassmorphism Spec:** `background: rgba(255, 255, 255, 0.04)`, `backdrop-filter: blur(16px)`, `border: 1px solid rgba(255, 255, 255, 0.08)`.

---

## 5. Components

### Buttons
*   **Primary:** Background: `primary_container`; Text: `on_primary_container`; Corner-radius: `xl` (24px).
*   **Secondary (Ghost):** Background: Transparent; Border: 1px `outline_variant` at 20%; Text: `primary`.
*   **Interaction:** On hover, primary buttons should increase their `backdrop-blur` or slightly shift color toward `primary_fixed_dim`.

### Cards & Lists
*   **Constraint:** Zero dividers. Use vertical white space (32px, 48px, or 64px) to separate content.
*   **Project Cards:** Use `rounded-2xl` (16px). Images should have a subtle `inner-shadow` to look recessed into the card surface.

### Navigation (Fixed Glass)
*   **Default:** Transparent background, `body-md` typography.
*   **Scrolled:** Transition to `surface_container_lowest` at 80% opacity with a `backdrop-filter: blur(20px)`. This creates a "frosted obsidian" effect that allows content to pass underneath elegantly.

### Signature Component: The "Project Badge"
*   **Style:** `rounded-full`, typography `label-sm`, background `surface_variant`. Use these for tech stacks (e.g., React, TypeScript) to keep the layout feeling organized and modular.

---

## 6. Do's and Don'ts

### Do:
*   **Do** use extreme white space. If a section feels crowded, double the padding.
*   **Do** use `primary` accents sparingly—only for primary CTAs and active states.
*   **Do** favor asymmetric layouts (e.g., a headline on the left, body text offset to the right).

### Don't:
*   **Don't** use 100% white (`#FFFFFF`). Always use `on_surface` (`#e4e1e9`) to prevent eye strain.
*   **Don't** use sharp corners. Everything in this system uses `md`, `lg`, or `xl` rounding to feel organic.
*   **Don't** use standard "drop shadows" on cards. Use background-color contrast or glass effects instead.