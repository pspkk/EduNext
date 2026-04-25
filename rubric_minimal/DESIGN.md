# Design System Specification: The Digital Curator

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Curated Monolith."** 

This system rejects the cluttered, "boxed-in" aesthetic of traditional digital libraries in favor of a high-end editorial experience. It draws inspiration from avant-garde architectural journals and premium archival catalogs. By leveraging intentional asymmetry, expansive white space, and a high-contrast color palette, we transform a simple database into a prestigious digital environment. 

We break the "template" look by treating the screen as a canvas rather than a grid. Elements should feel weighted and permanent, using the vibrant red (`primary`) as a surgical tool for navigation and action, while the grey scale provides a sophisticated, academic structure.

## 2. Colors
Our palette is rooted in a "High-Contrast Minimalist" philosophy. The interaction between the stark white background and the deep, vibrant red creates a sense of urgency and importance, while the neutral greys provide the necessary academic "breathing room."

### Color Strategy
- **Primary Action (`primary` - #af101a):** This is our signature "Red Ink." It should be used sparingly but boldly. Reserve it for critical CTAs, active states, and essential navigational signposts.
- **Surface & Hierarchy:** We utilize the `surface` tokens to define the environment. The base is `surface` (#f9f9f9), providing a softer, more professional white than pure `#ffffff`.
- **The "No-Line" Rule:** Under no circumstances are 1px solid borders to be used for sectioning or layout division. Structural boundaries must be defined through tonal shifts. For example, a sidebar should be rendered in `surface_container_low` (#f3f3f3) against the `surface` background, creating a clean, seamless transition.

### Glass & Gradient Implementation
- **The Signature Gradient:** For hero sections or primary action containers, use a subtle linear gradient transitioning from `primary` (#af101a) to `primary_container` (#d32f2f). This adds "soul" and depth, preventing the red from feeling flat or aggressive.
- **Glassmorphism:** Floating menus and modals should use `surface_container_lowest` (#ffffff) at 80% opacity with a `20px` backdrop-blur. This ensures the academic content remains visible but softly recedes, maintaining a sense of layered physical space.

## 3. Typography
The typography is a dialogue between the geometric authority of **Manrope** and the functional precision of **Inter**.

- **Display & Headlines (Manrope):** These are our "Editorial Statements." Use `display-lg` for page entries to create an immediate sense of scale. The tracking should be slightly tightened (-0.02em) to feel more "custom."
- **Body & Labels (Inter):** Inter handles the "Academic Weight." Its high x-height ensures readability for long-form library descriptions. 
- **Hierarchy as Identity:** By pairing a large `display-md` title with a significantly smaller `label-md` metadata tag (in `secondary`), we create a sophisticated contrast that mirrors high-end print design.

## 4. Elevation & Depth
In this system, depth is a result of layering materials, not "dropping shadows."

- **The Layering Principle:** Use the `surface-container` tiers to create hierarchy. 
    - Level 0: `surface` (The Floor)
    - Level 1: `surface_container_low` (In-set content areas)
    - Level 2: `surface_container_highest` (Active card or focused element)
- **Ambient Shadows:** When an element must float (e.g., a dropdown), use a shadow tinted with `on_surface` (#1a1c1c). Specification: `0px 12px 32px rgba(26, 28, 28, 0.06)`. It should feel like a soft, natural glow, not a dark smudge.
- **The "Ghost Border" Fallback:** If containment is required for accessibility (e.g., input fields), use the `outline_variant` (#e4beba) at 15% opacity. This creates a "suggestion" of a boundary that disappears into the background.

## 5. Components

### Buttons
- **Primary:** Filled with `primary` (#af101a), text in `on_primary` (#ffffff). Use `md` (0.375rem) roundedness for a precise, "machined" feel.
- **Secondary:** `surface_container_high` background with `on_surface` text. No border.
- **Tertiary:** Text-only in `primary`, using a `title-sm` font weight for emphasis without the visual weight of a box.

### Cards & Collections
- **The "Un-Card":** Forbid the use of white boxes with shadows. Instead, represent library items as raw content blocks on the `surface`. Use `surface_container_low` as a hover state to reveal the item’s footprint. 
- **Dividers:** Do not use line dividers. Use `2.5rem` of vertical white space to separate thematic sections.

### Search & Input Fields
- **The Academic Input:** Use `surface_container_lowest` with a "Ghost Border." Upon focus, the border disappears and is replaced by a `2px` bottom-only stroke in `primary`.
- **Chips:** Use `secondary_container` (#d7e4ec) for filter chips with `full` (9999px) roundedness to contrast against the sharp, architectural lines of the rest of the UI.

### Navigation (The Sidebar)
- Use a persistent column in `surface_container_low`. Active links are signaled by a `primary` vertical "nib" (4px width) on the left, rather than highlighting the whole row.

## 6. Do's and Don'ts

### Do
- **Do** use intentional asymmetry. Offset your main content column to the right to create an editorial "gutter" on the left.
- **Do** prioritize white space. If you think there is enough space, add 20% more.
- **Do** use `primary` for "intent." If a user needs to click it to progress, it should likely involve the red palette.

### Don't
- **Don't** use 100% black text. Always use `on_surface` (#1a1c1c) to maintain a professional, soft-contrast feel.
- **Don't** use "Standard" 1px borders. If you find yourself reaching for a border tool, ask if a background color shift or a change in spacing could solve the problem.
- **Don't** use the `primary` color for large background areas. It is an accent/action color; overusing it will fatigue the user and destroy the "minimalist" aesthetic.