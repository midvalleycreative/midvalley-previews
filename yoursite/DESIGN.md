# Design System Strategy: The Kinetic Frame

### 1. Overview & Creative North Star
**Creative North Star: "The Kinetic Frame"**
This design system rejects the "standard" retail template in favor of an editorial, high-contrast experience. By framing vibrant, energetic brand colors within a deep, monolithic black architecture (#0B0B0B), we create a sense of theater and prestige. The "Kinetic Frame" utilizes the tension between vast, crisp white spaces (`surface`) and surgical strikes of Brazilian Green and Yellow to guide the user’s eye with intentionality. We move away from flat, boxed UI toward a layered, architectural approach where depth is felt through tonal shifts rather than seen through lines.

---

### 2. Color & Surface Architecture
The color palette is a sophisticated evolution of the Brazilian spirit—energetic yet disciplined.

*   **Primary Momentum (`primary` / #006b26):** Used for primary actions and semantic headings. It represents growth and authority.
*   **The Golden Spark (`secondary_container` / #fddc00):** Our accent. Use this sparingly (the "1% Rule"). It is for small call-outs, high-priority highlights, or secondary buttons that need to "pop" against the green.
*   **The Monolith (`inverse_surface` / #313030 & Header/Footer):** Solid black frames the content, providing a premium "anchor" that prevents the vibrant colors from feeling "sporty" or "casual."

**The "No-Line" Rule**
Standard 1px borders are strictly prohibited for sectioning. Definition must be achieved through background shifts. For example, a `surface-container-low` section should sit on a `surface` background to create a boundary. This creates a softer, more high-end transition that feels "built" rather than "drawn."

**Surface Hierarchy & Nesting**
Treat the UI as a series of stacked physical layers.
*   **Base:** `surface` (#fcf8f8) for the main canvas.
*   **Elevated Elements:** Use `surface-container-lowest` (#ffffff) for cards or "floating" modules to create a subtle lift.
*   **Recessed Elements:** Use `surface-container-high` (#ebe7e7) for search bars or inset utility areas.

**The Glass & Gradient Rule**
To add "soul" to the layout, primary buttons and hero sections should utilize a subtle linear gradient—transitioning from `primary` (#006b26) to `primary_container` (#008732). For overlays or floating navigation bars, use Glassmorphism: a semi-transparent `surface` color with a 20px backdrop-blur to allow the content beneath to bleed through rhythmically.

---

### 3. Typography: Editorial Authority
We use **Manrope** to bridge the gap between technical precision and human warmth.

*   **Display & Headlines:** Use `display-lg` and `headline-lg` with a "bold" weight. Large-scale typography is a core brand asset; headlines should be treated as graphic elements. Use `on_surface` (#1c1b1b) for most text, but leverage `primary` (#006b26) for short, punchy headlines to inject energy.
*   **The Body Scale:** `body-lg` (1rem) is our standard for readability. Maintain generous line-heights (1.6x) to ensure the high-contrast colors don't cause eye fatigue.
*   **Labels:** `label-md` and `label-sm` should be used for metadata and small UI indicators, often in all-caps with slightly increased letter spacing (0.05rem) to maintain a premium feel.

---

### 4. Elevation & Depth
Depth in this system is a result of light and shadow, not lines.

*   **The Layering Principle:** Achieve hierarchy by "stacking." A `surface-container-lowest` card placed atop a `surface-container-low` section creates a natural, soft lift.
*   **Ambient Shadows:** When an element must float (e.g., a "Buy" button or a Modal), use a diffused shadow.
    *   **Blur:** 24px - 40px.
    *   **Opacity:** 4% to 6%.
    *   **Color:** Use a tinted version of `on_surface` to simulate natural light.
*   **The Ghost Border Fallback:** If accessibility requires a container boundary, use a "Ghost Border": the `outline_variant` token at 15% opacity. Never use a 100% opaque border.

---

### 5. Components

*   **Buttons:**
    *   *Primary:* Solid `primary` gradient with `on_primary` (#ffffff) text. Roundness: `DEFAULT` (0.25rem).
    *   *Secondary:* Solid `secondary_container` (#fddc00) with `on_secondary_container` (#706000) text. This is high-visibility.
    *   *Tertiary:* Transparent background with `primary` text. No border; use padding to define the hit area.
*   **Input Fields:**
    *   Use `surface-container-low` as the field background.
    *   No bottom line or full outline. Use a "Ghost Border" that becomes `primary` (2px) only on focus.
*   **Cards:** 
    *   Never use dividers. Separate content using the spacing scale (e.g., 24px padding between elements).
    *   Background should be `surface-container-lowest` to provide a "clean white" contrast against the off-white `surface`.
*   **Chips:**
    *   Use `primary_fixed` for a soft, low-contrast background with `on_primary_fixed_variant` text for selection states. Keep them subtle so they don't compete with main CTAs.
*   **Contextual Nav (The Frame):**
    *   Header and Footer must be the solid "Monolith" black (#0B0B0B). Use `surface_variant` at 20% opacity for any necessary icons or links within these areas to keep them "quiet."

---

### 6. Do's and Don'ts

**Do:**
*   **Do** use asymmetrical layouts. Let an image bleed off the edge of the screen while text remains anchored to the grid.
*   **Do** use the `secondary` yellow for "Micro-Moments"—a notification dot, a price tag, or a star rating.
*   **Do** prioritize whitespace. The "premium" feel comes from the space you *don't* fill.

**Don't:**
*   **Don't** use a 1px divider to separate list items. Use 16px of vertical whitespace or a 1-step shift in surface color.
*   **Don't** use the Green and Yellow in equal proportions. This will create the "party" vibe we are avoiding. Green is the hero; Yellow is the spotlight.
*   **Don't** use standard "Drop Shadows" (Black/Grey). Always tint your shadows to match the background they sit on for a "High-End Editorial" finish.