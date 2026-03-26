# Design System Specification: High-End Editorial

## 1. Overview & Creative North Star
This design system is built upon a Creative North Star we define as **"The Precision Curator."** 

While the functional building blocks are rooted in corporate, enterprise-grade logic, the execution is purely editorial. For a premium automotive webshop, we move beyond the "catalog" look and toward a "gallery" experience. The system breaks traditional, rigid grid structures through intentional white space, high-contrast typographic scales, and layered surfaces. We treat every vehicle and component as an artifact of engineering, using spaciousness and subtle tonal shifts to command authority and trust.

## 2. Colors & Surface Logic
The palette is dominated by neutral whites and sophisticated grays, punctuated by a commanding `primary` blue.

### Surface Hierarchy & The "No-Line" Rule
To achieve a premium, custom feel, we explicitly prohibit the use of 1px solid borders for sectioning. 
- **The Rule:** Boundaries between content areas must be defined solely through background color shifts or spacing.
- **Nesting Tiers:** Use the `surface-container` tokens to create depth. A `surface-container-lowest` (#ffffff) card should sit atop a `surface-container-low` (#f2f4f6) section. This creates a soft, natural distinction that feels architectural rather than "templated."
- **The Glass & Gradient Rule:** For floating elements like navigation bars or quick-action menus, use semi-transparent variations of `surface` with a `backdrop-blur` effect. For high-impact CTAs, utilize a subtle linear gradient from `primary` (#0037b0) to `primary_container` (#1d4ed8) to add a sense of "visual soul."

### Color Tokens (Selection)
| Token | Value | Role |
| :--- | :--- | :--- |
| `primary` | #0037b0 | Actionable elements, brand presence. |
| `surface` | #f7f9fb | Main background; clean, airy foundation. |
| `surface_container_low` | #f2f4f6 | Secondary sectioning backgrounds. |
| `surface_container_lowest`| #ffffff | Elevated card surfaces. |
| `outline_variant` | #c4c5d7 | For "Ghost Borders" only (at <20% opacity). |

## 3. Typography
We utilize **Inter** to bridge the gap between technical precision and human readability.

- **Display & Headline:** Use `display-lg` (3.5rem) and `headline-lg` (2rem) with tight letter-spacing for hero sections. These should feel authoritative and "poster-like."
- **Title & Body:** `title-lg` (1.375rem) serves as the primary entry point for content blocks. `body-lg` (1rem) is the workhorse for vehicle specifications and descriptions, ensuring clarity.
- **Labeling:** `label-md` (0.75rem) is used for technical metadata (e.g., fuel type, horsepower) to provide a high-density information layer without cluttering the visual field.

## 4. Elevation & Depth
Depth in this system is a result of **Tonal Layering**, not structural artifice.

- **The Layering Principle:** Stack `surface_container` tiers to create hierarchy. A vehicle configuration panel should use a slightly higher tier than the main shop floor to indicate active focus.
- **Ambient Shadows:** Shadows must be felt, not seen. Use extra-diffused blur values (20px+) at 4-6% opacity. The shadow color must be a tinted version of `on_surface` to mimic natural light scattering on a premium material.
- **The Ghost Border:** If accessibility requires a border, use the `outline_variant` token at a maximum of 20% opacity. 100% opaque borders are strictly forbidden as they interrupt the "Precision Curator" flow.

## 5. Components

### Buttons
- **Primary:** Filled with `primary` blue. Use `rounded-md` (0.75rem) for a balance between corporate stability and modern friendliness. 
- **Secondary/Outlined:** Use a "Ghost Border" (20% opacity) or a subtle `surface_container_high` background.
- **Interaction:** On hover, transition to `on_primary_fixed_variant` to signal depth change.

### Navigation & Segmented Tabs
- **Mechanism:** Use a clear `primary` underline (2px thickness) for active states.
- **Visuals:** Inactive tabs should use `on_surface_variant` at 60% opacity to ensure the active selection is the undisputed hero of the layout.

### Form Elements & Search
- **Search Bars:** Rounded containers using `surface_container_low` with a prominent `primary` icon.
- **Input Fields:** Forgo the 4-sided box; use a "bottom-line" approach or a very subtle background fill (`surface_container_lowest`) to maintain the editorial feel.

### Cards & Lists
- **Forbid Dividers:** Do not use horizontal lines to separate list items. Use the **Spacing Scale** (token `5` or `6`) to create a clear "gutter" of white space, or alternate between `surface` and `surface_container_low`.
- **Nesting:** All vehicle cards must be `surface_container_lowest` (#ffffff) to "pop" against the foundational `surface` background.

## 6. Do's and Don'ts

### Do:
- **Use Intentional Asymmetry:** Offset vehicle images from text blocks to create a dynamic, editorial flow.
- **Embrace the Gutter:** Use large spacing values (`16` or `20`) between major content sections to allow the design to "breathe."
- **Layer with Purpose:** Only elevate elements that require immediate user interaction.

### Don't:
- **No 1px Black Borders:** Never use high-contrast lines to divide space; it creates "visual noise" that breaks the premium feel.
- **Avoid Flatness:** Don't let the "Corporate" requirement lead to a flat, 2D layout. Use the `surface` hierarchy to create a tactile, layered environment.
- **No Default Shadows:** Never use the standard CSS `0 2px 4px rgba(0,0,0,0.5)`. It is too heavy for this high-end aesthetic.