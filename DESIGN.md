# Design System Strategy: High-End Editorial Real Estate

## 1. Overview & Creative North Star: "The Architectural Monolith"
The Creative North Star for this design system is **The Architectural Monolith**. This concept treats the digital interface not as a website, but as a physical gallery space—a series of curated, high-ceilinged rooms where every property is a work of art. 

We break the "template" look by rejecting the traditional 12-column grid in favor of **intentional asymmetry**. Images should bleed off the edge of the container, and typography should overlap visual elements to create a sense of three-dimensional depth. This is an editorial experience: we value white space as much as the content itself. We do not fill gaps; we celebrate them.

---

## 2. Colors & Tonal Logic
The palette is rooted in natural, mineral tones. It is designed to feel expensive, quiet, and stable.

### The "No-Line" Rule
Traditional 1px solid borders are strictly prohibited for sectioning content. To define boundaries, designers must use **Background Color Shifts**. For example, a property detail section using `surface-container-low` should sit directly against a `surface` background. The shift in tone provides a sophisticated, "borderless" containment.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked fine papers. 
- **Surface (`#f9f9f7`)**: The base floor of the gallery.
- **Surface-Container-Low (`#f2f4f2`)**: Used for large structural background shifts.
- **Surface-Container-Lowest (`#ffffff`)**: Reserved for high-priority floating elements or "cards" that need to pop from the background.
- **Surface-Container-Highest (`#dee4e0`)**: Used for small, interactive elements like search bars or inactive tabs.

### The "Glass & Gradient" Rule
To avoid a flat "Bootstrap" feel, use **Glassmorphism** for floating navigation and filter bars. 
- Use `surface` at 80% opacity with a `backdrop-blur` of 20px. 
- **Signature Textures:** Apply a subtle linear gradient to main CTAs (from `primary` to `primary-dim`) to give buttons a slight metallic sheen, mimicking high-end architectural hardware.

---

## 3. Typography: The Editorial Voice
Our typography creates an immediate sense of authority and prestige.

- **Display & Headlines (Noto Serif / Playfair Display):** These are our "Statement Pieces." Use `display-lg` (3.5rem) with tightened letter-spacing (-0.02em) for hero headlines. Use `headline-sm` for property titles to evoke the feel of a luxury magazine masthead.
- **Body & Labels (Inter):** The "Functional Layer." Inter provides a clean, neutral counterpoint to the serif headings. 
- **The Hierarchy Strategy:** Always pair a large Serif headline with a significantly smaller Sans-Serif label (`label-md`). This high contrast in scale—not just weight—is the hallmark of high-end editorial design.

---

## 4. Elevation & Depth
Depth in this system is achieved through light and layering, never through heavy shadows.

- **The Layering Principle:** Instead of shadows, stack containers. Place a `surface-container-lowest` card on top of a `surface-container-low` section. The contrast in brightness creates a "Soft Lift."
- **Ambient Shadows:** When a shadow is required (e.g., a floating property inquiry form), use an ultra-diffused shadow: `box-shadow: 0 20px 50px rgba(45, 52, 50, 0.04)`. The color is a tinted version of `on-surface`, making it feel like a natural light obstruction rather than a digital effect.
- **The Ghost Border:** If a visual boundary is required for accessibility (like an input field), use a "Ghost Border": `outline-variant` at 20% opacity. Never use 100% opacity for lines.

---

## 5. Components

### Buttons: The "Gallery Label" Style
- **Primary:** `surface-tint` background with `on-primary` text. No rounded corners (`0px`). Use `spacing-6` for horizontal padding to create an elongated, elegant silhouette.
- **Secondary:** Transparent background with a `Ghost Border`. On hover, transition to a `surface-container-highest` background with a subtle `0.5s` ease.
- **Tertiary:** Text only in `primary`, using `label-md` with 1px letter spacing.

### Input Fields: The "Architectural Ledger"
- Remove all borders except for a subtle bottom-border (Ghost Border style).
- Labels must use `label-sm` and remain visible above the input, never as placeholder text, to maintain an "official" feel.

### Cards & Property Lists
- **Prohibition of Dividers:** Do not use lines to separate list items. Use `spacing-12` to `spacing-16` (4rem to 5.5rem) of vertical white space to create separation.
- **Image Treatment:** Use `0px` radius for all property imagery. Images should be the primary driver of the layout’s "weight."

### Signature Component: The "Perspective Peek"
A custom component for real estate: A large-scale image slider where the next property is partially visible (20%) at the edge of the screen, breaking the centered grid and encouraging exploration through asymmetry.

---

## 6. Do’s and Don’ts

### Do:
- **Use "Aggressive" White Space:** If a section feels finished, add 2rem more spacing. 
- **Embrace the Mono-Corner:** Use `0px` for every single element. Roundness is for consumer apps; sharp edges are for high-end architecture.
- **Tonal Transitions:** Transition between sections using the `surface-container` scale (e.g., moving from `surface` to `surface-container-low`).

### Don’t:
- **Don't use 1px solid black/gray borders.** Use background color shifts or Ghost Borders.
- **Don't use standard "Blue" for links.** Trust is built through the `charcoal (#2D2D2A)` and `warm gray (#8C8C88)` tones.
- **Don't center-align long blocks of text.** Editorial design is almost always left-aligned or uses a custom staggered layout.
- **Don't use "Drop Shadows" on text.** If text isn't legible, adjust the overlay opacity or the background tone, not the shadow.