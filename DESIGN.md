# Design System Document: High-Tech Laboratory Editorial

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Kinetic Chronosphere."**

We are moving away from the "standard mobile game" aesthetic of flat buttons and rigid grids. Instead, we are building a high-end, immersive laboratory interface that feels like a live holographic projection. This system prioritizes **intentional asymmetry** and **tonal depth**. By overlapping translucent surfaces and using high-contrast typography scales, we create an environment that feels both scientifically precise and energetically vibrant. Every element should feel like it is "powered" by the neon cubes it houses.

## 2. Colors & Surface Logic
The palette transitions from the deep, atmospheric void of a laboratory into the high-energy output of experimental neon.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections. Boundaries must be established through:
*   **Background Shifts:** Using `surface-container-low` against a `surface` background.
*   **Tonal Transitions:** Defining an area by its container’s depth rather than a stroke.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked, frosted glass panes.
*   **Base Layer:** `surface` (#0c0c21) acts as the deep laboratory floor.
*   **Nesting:** Place a `surface-container-low` (#111128) panel on the base, then nest a `surface-container-high` (#1d1d39) card inside it to denote interactive importance. This "step-up" logic creates natural focus without visual clutter.

### The "Glass & Gradient" Rule
To capture the "high-tech lab" essence, floating panels must utilize **Glassmorphism**.
*   Use `surface-variant` (#232341) at 60% opacity with a `backdrop-filter: blur(12px)`.
*   **Signature Textures:** For primary CTAs and hero states, use a linear gradient transitioning from `primary` (#8ff5ff) to `primary-container` (#00eefc) at a 135-degree angle. This provides a "shimmer" effect that mimics light passing through a glowing cube.

## 3. Typography
The typography strategy pairs the technical precision of **Space Grotesk** with the human-centric readability of **Manrope**.

*   **Display & Headlines (Space Grotesk):** These are your "Data Readouts." Use `display-lg` for big, bold impact during level wins or high-score moments. The exaggerated geometry of Space Grotesk mirrors the futuristic, monospaced feel of lab equipment.
*   **Body & Titles (Manrope):** These are your "Lab Reports." Manrope provides a clean, neutral balance to the aggressive energy of the neon accents.
*   **Labels (Space Grotesk):** Small UI labels use the monospaced-adjacent feel of Space Grotesk to imply technical metadata or coordinate systems.

## 4. Elevation & Depth
In a world of light and glass, shadows are not black; they are "ambient glows."

*   **The Layering Principle:** Achieve lift by stacking surface tiers. A `surface-container-lowest` card placed on a `surface-container-low` section creates a recessed, "slotted-in" look, perfect for inventory slots.
*   **Ambient Shadows:** For floating elements, use a shadow with a blur of 30px-40px and an opacity of 6%. The shadow color must be a tinted version of `on-surface` (#e5e3ff), creating a soft, blue-toned atmospheric haze rather than a muddy grey.
*   **The "Ghost Border":** If a separation is functionally required, use the `outline-variant` (#46465e) token at **15% opacity**. This creates a "light-leak" edge rather than a hard boundary.

## 5. Components

### Buttons
*   **Primary (The Power Core):** High-gloss finish. Background: `primary` gradient. Text: `on-primary` (#005d63). Use `rounded-md` (0.375rem) for a precision-engineered look.
*   **Secondary (The Sub-System):** Background: `secondary-container` (#a900a9). Text: `on-secondary-container`. This provides a sharp magenta contrast to the cyan primary.
*   **Tertiary (The Ghost):** No background. `primary` text with a subtle `primary-dim` outer glow on hover/active states.

### Progress Bars (Energy Conduits)
*   **Track:** `surface-container-highest` (#232341).
*   **Fill:** A bi-color gradient from `tertiary` (#bcff5f) to `primary` (#8ff5ff).
*   **Effect:** Add a 2px inner glow to the fill to make it look like liquid neon flowing through a tube.

### Cards & Lists
*   **Rule:** Forbid the use of divider lines.
*   **Implementation:** Separate list items using 8px of vertical white space and a subtle background shift to `surface-container-low`. For selected states, use a `primary` glow on the left edge (2px width).

### Laboratory-Specific Components
*   **Cube Slots:** Use `surface-container-lowest` with an inner shadow to create a "recessed" physical socket where vibrant cubes are placed.
*   **Status Tags:** Small, semi-transparent pills using `tertiary` (#bcff5f) for "Stable" or `error` (#ff716c) for "Unstable/Critical" states.

## 6. Do's and Don'ts

### Do:
*   **Embrace Asymmetry:** Align technical data to the right while headlines sit on the left to create a "HUD" (Heads-Up Display) feel.
*   **Use Tonal Layering:** Always check if a color shift can replace a border.
*   **Leverage Transparency:** Let the background `surface` colors bleed through your UI panels to maintain environmental immersion.

### Don't:
*   **Use Pure Black/White:** Use the palette's deep blues (`surface`) and tinted whites (`on-surface`) to keep the "lab glow" alive.
*   **Default to 'Shadows':** Don't use standard drop shadows on cards; use background color elevation first.
*   **Clutter with Borders:** Never use 100% opaque `outline` tokens for containers; it breaks the "holographic" illusion.