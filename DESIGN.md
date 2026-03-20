# Design System Strategy: The Artisanal Assemblage

## 1. Overview & Creative North Star
The Creative North Star for this system is **"The Artisanal Assemblage."** 

We are moving away from the rigid, sterile grids of traditional tech and toward the tactile elegance of a Parisian pâtisserie atelier. The interface should feel like a beautifully plated dish—intentional, layered, and slightly asymmetrical. We achieve a "Playful Premium" aesthetic by balancing the editorial weight of serif typography with a warm, "social-native" layout that invites touch. 

To break the "template" look, designers must embrace overlapping elements (e.g., a high-gloss food photo bleeding off the edge of a container) and high-contrast typography scales that feel more like a lifestyle magazine than a mobile app.

---

## 2. Colors & Surface Philosophy
The palette is rooted in gourmet ingredients. Our goal is to create a "warm-inclusive" atmosphere where depth is felt through color temperature rather than structural lines.

### The "No-Line" Rule
**Explicit Instruction:** Use of 1px solid borders for sectioning is strictly prohibited. 
Boundaries must be defined solely through background color shifts or subtle tonal transitions. For example, a `surface-container-low` (#faf2ec) section should sit on a `surface` (#fff8f3) background to create a soft, natural break.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of fine parchment or ceramic plates.
- **Base:** `surface` (#fff8f3) with a subtle 2% grain texture.
- **Secondary Containers:** Use `secondary_fixed` (#ffd9e2) for cards to create a "Powder Pink" pop.
- **Nesting:** To highlight a specific element within a pink card, use a `surface_container_lowest` (#ffffff) inset rather than a border.

### The "Glass & Gradient" Rule
To elevate the experience beyond flat design, use **Glassmorphism** for floating elements (like the sticky bottom bar). Use the `surface` color at 80% opacity with a 12px backdrop-blur. 
For Main CTAs (`primary` #9e3944), apply a subtle linear gradient transitioning to `primary_container` (#be515b) to simulate the "glossy" finish of a cherry coulis.

---

## 3. Typography: Editorial Authority
Our typography is a conversation between tradition (Fraunces) and modern energy (Space Grotesk).

- **Titles (Fraunces):** Use for headlines and "editorial" moments. Its soft serifs convey the "Atelier" personality. Use tight letter-spacing (-2%) for large display sizes to feel premium.
- **Body (Plus Jakarta Sans):** Our workhorse. It is mobile-first and warm. Use it for all long-form content and descriptions to ensure maximum legibility.
- **Labels & Data (Space Grotesk):** This adds "Contemporary Energy." Use this for prices, timestamps, and nutritional badges. Its technical nature balances the softness of the other two fonts.

---

## 4. Elevation & Depth
We eschew traditional "material" shadows in favor of **Tonal Layering**.

- **The Layering Principle:** Depth is achieved by stacking `surface-container` tiers. A `surface-container-highest` element should feel "closer" to the user than a `surface-container-low` element.
- **Ambient Shadows:** When an element must float (e.g., a "Reserve" button), use an extra-diffused shadow. 
    *   *Blur:* 24px - 40px
    *   *Opacity:* 5% 
    *   *Color:* Use a tinted version of `Cocoa Mocha` (#5B342D) to mimic natural light, never pure grey.
- **The "Ghost Border" Fallback:** If accessibility requires a container definition, use the `outline_variant` token at 15% opacity. It should be felt, not seen.

---

## 5. Components

### The "Ceramic" Button
- **Primary:** `primary` (#9e3944) background with `on_primary` (#ffffff) text.
- **Shape:** Use `rounded-xl` (1.5rem) to mimic the soft edges of hand-thrown ceramics.
- **Interaction:** On press, the button should scale down slightly (98%) rather than just changing color, providing a tactile, "squishy" feel.

### Sticky Bottom Tray (Mobile-First)
The primary CTA bar must be sticky at the bottom of the viewport.
- **Background:** Glassmorphic `surface` with backdrop-blur.
- **Content:** An asymmetrical layout—Price on the left (Space Grotesk), Main Action on the right (Cherry Coulis Button).

### Artful Cards
- **Construction:** Use `secondary_fixed` (#ffd9e2) for the container.
- **Imagery:** Photos must be "Glossy Food Style"—high contrast, high saturation. 
- **Separation:** Forbid the use of divider lines. Use `spacing-6` (2rem) of vertical white space to separate the image from the text description.

### Signature Badges
- **Pistachio Freshness:** Use `tertiary_fixed` (#cfeac7) for status indicators (e.g., "Available Today").
- **Butter Highlights:** Use `Butter Yellow` (#F5D889) specifically for ratings or "Chef's Choice" stars.

---

## 6. Do's and Don'ts

### Do
- **Use Intentional Asymmetry:** Overlap a "Fine painted stroke" doodle over the corner of a photo.
- **Embrace White Space:** Use the `spacing-12` and `spacing-16` tokens generously to let the "Editorial" typography breathe.
- **Grain is Essential:** Ensure the subtle grain texture is present on all large `Cream Milk` surfaces to avoid a "flat-web" look.

### Don't
- **No Hard Edges:** Avoid `rounded-none` or `rounded-sm`. Everything should feel organic and soft.
- **No Pure Black:** Never use #000000. Use `Cocoa Mocha` (#5B342D) for all "black" text to maintain warmth.
- **No Default Dividers:** If you feel the need to add a horizontal line, instead try increasing the background contrast between two sections or adding a `spacing-8` gap.