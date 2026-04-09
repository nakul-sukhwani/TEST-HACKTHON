# Design System Specification: The Clinical Sentinel

## 1. Overview & Creative North Star
The "Clinical Sentinel" is the creative North Star of this design system. We are moving away from the generic "utility app" look and toward a high-end, editorial safety portal that feels authoritative, academic, and hyper-responsive. 

This system rejects the rigid, boxy constraints of standard dashboards. Instead, it utilizes **Organic Authority**—a blend of sophisticated typography, intentional asymmetry, and deep tonal layering. The interface should feel like a premium piece of glass held over a campus map: transparent, precise, and vital. We break the "template" look by using exaggerated typographic scales and overlapping map modules that ignore standard grid gutters to create a sense of urgency and modern sophistication.

---

## 2. Colors & Surface Logic
The palette is rooted in institutional trust (`primary`) and critical response (`tertiary`). 

### The "No-Line" Rule
To achieve a premium editorial feel, **1px solid borders are strictly prohibited for sectioning.** Boundaries must be defined through background color shifts. For example, a `surface_container_low` card should sit on a `surface` background to define its shape. We use contrast, not lines, to provide structure.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of semi-translucent materials.
*   **Base:** `surface` or `background`
*   **Level 1 (Sections):** `surface_container_low`
*   **Level 2 (Active Modules):** `surface_container_highest`
*   **Level 3 (Floating Overlays):** `surface_container_lowest` (white) for maximum pop.

### The "Glass & Gradient" Rule
Floating action panels and SOS modules should utilize **Glassmorphism**. Apply `surface_variant` at 70% opacity with a `20px` backdrop blur. 
*   **Signature Textures:** Use a subtle linear gradient (45-degree) from `primary` to `primary_container` for hero CTAs to provide "visual soul" and depth that prevents the UI from looking flat or "default."

---

## 3. Typography: Editorial Authority
We pair **Manrope** (Display/Headlines) with **Inter** (Body/Labels) to balance academic prestige with technical clarity.

*   **Display & Headlines (Manrope):** Use `display-lg` and `headline-lg` with tight letter-spacing (-0.02em) to create an authoritative, "breaking news" feel. Use `headline-sm` for category headers (Toilets, Food, Water) to give them a distinct, bold presence.
*   **Body & Titles (Inter):** Use `body-md` for high-density information. The Inter font provides the "transparency" required for safety instructions—it disappears so the content can lead.
*   **Labeling:** `label-sm` should be used for status indicators, always in uppercase with `0.05em` tracking for a technical, "instrument panel" aesthetic.

---

## 4. Elevation & Depth
Depth is achieved through **Tonal Layering** rather than traditional drop shadows.

*   **The Layering Principle:** To lift a hygiene report card, place a `surface_container_lowest` card on a `surface_container` background. The subtle shift in hex code creates a natural, soft lift.
*   **Ambient Shadows:** If a floating element (like an SOS button) requires a shadow, use a large blur (32px) at 6% opacity using a tint of `on_surface` (a deep navy/gray) rather than pure black. This mimics natural light.
*   **The "Ghost Border" Fallback:** For accessibility in high-glare outdoor environments, use a "Ghost Border": `outline_variant` at 15% opacity. Never 100%.

---

## 5. Components

### Buttons
*   **Primary (Urgent):** Gradient from `primary` to `primary_container`. `xl` (0.75rem) roundedness. Text in `on_primary`.
*   **Secondary (Admin):** `surface_container_highest` background with `on_surface_variant` text. No border.
*   **SOS/Tertiary:** `tertiary` background. This is the only element allowed to use high-saturation red to signal extreme urgency.

### Input Fields
Use `surface_container_low` as the field background. The active state should not use a heavy border; instead, use a 2px `primary` underline or a subtle `outline` shift. Labels use `label-md` tucked 4px above the input.

### Status Chips
*   **Critical:** `tertiary_container` background with `on_tertiary_container` text.
*   **Safe:** `primary_fixed` background with `on_primary_fixed` text.
*   Shape: Use `full` (pill) roundedness to distinguish chips from the `lg` roundedness of cards.

### Cards & Lists
*   **Forbid dividers.** To separate hygiene logs, use 16px of vertical whitespace or alternating backgrounds between `surface_container_low` and `surface_container_lowest`.
*   **Asymmetric Maps:** Map integrations should bleed to the edge of the screen on at least one side, with "Clinical Sentinel" floating UI cards overlapping the map edges to create a layered, multi-dimensional feel.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use `manrope` for large numerical data (e.g., "98% Cleanliness").
*   **Do** lean into white space. If a screen feels "full," increase the spacing scale rather than adding lines.
*   **Do** use "Ambient Shadows" only for elements that are physically "above" the map (e.g., navigation or SOS).

### Don't:
*   **Don't** use 1px solid borders to separate navigation from content. Use a `surface_bright` to `surface_dim` transition.
*   **Don't** use standard "Alert Red" for everything. Reserve the `tertiary` palette exclusively for life-safety or hygiene failures. 
*   **Don't** use default Inter "Medium" for everything. Use the contrast between Manrope Bold and Inter Regular to create a high-end editorial hierarchy.

### Accessibility Tip:
When using Glassmorphism, ensure the `on_surface` text maintains a 4.5:1 contrast ratio against the blurred background. If the background is too busy, increase the opacity of the `surface_container` layer.