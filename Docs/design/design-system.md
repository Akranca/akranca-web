---
name: Akranca Design System
colors:
  surface: '#f8f9fb'
  surface-dim: '#d8dadc'
  surface-bright: '#f8f9fb'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f2f4f6'
  surface-container: '#eceef0'
  surface-container-high: '#e6e8ea'
  surface-container-highest: '#e0e3e5'
  on-surface: '#191c1e'
  on-surface-variant: '#42474f'
  inverse-surface: '#2d3133'
  inverse-on-surface: '#eff1f3'
  outline: '#727780'
  outline-variant: '#c2c7d0'
  surface-tint: '#32618f'
  primary: '#21537f'
  on-primary: '#ffffff'
  primary-container: '#3d6b99'
  on-primary-container: '#dae9ff'
  inverse-primary: '#9ecafe'
  secondary: '#805600'
  on-secondary: '#ffffff'
  secondary-container: '#ffc161'
  on-secondary-container: '#754e00'
  tertiary: '#48515d'
  on-tertiary: '#ffffff'
  tertiary-container: '#606975'
  on-tertiary-container: '#e0e9f8'
  error: '#C0392B'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#d0e4ff'
  primary-fixed-dim: '#9ecafe'
  on-primary-fixed: '#001d35'
  on-primary-fixed-variant: '#144975'
  secondary-fixed: '#ffddb0'
  secondary-fixed-dim: '#f9bc5c'
  on-secondary-fixed: '#281800'
  on-secondary-fixed-variant: '#614000'
  tertiary-fixed: '#dae3f2'
  tertiary-fixed-dim: '#bec7d5'
  on-tertiary-fixed: '#131c26'
  on-tertiary-fixed-variant: '#3e4853'
  background: '#f8f9fb'
  on-background: '#191c1e'
  surface-variant: '#e0e3e5'
  blue-dark: '#2C4F73'
  blue-light: '#7A9CC0'
  blue-surface: '#DCE7F2'
  amber-light: '#F5CB8A'
  amber-surface: '#FDF0DC'
  text-secondary: '#5C6672'
  text-hint: '#939CA6'
  border-subtle: '#D5DAE0'
  success: '#3E7C4F'
typography:
  headline-lg:
    fontFamily: Space Grotesk
    fontSize: 32px
    fontWeight: '500'
    lineHeight: '1.2'
    letterSpacing: -0.02em
  headline-md:
    fontFamily: Space Grotesk
    fontSize: 24px
    fontWeight: '500'
    lineHeight: '1.3'
  headline-sm:
    fontFamily: Space Grotesk
    fontSize: 20px
    fontWeight: '500'
    lineHeight: '1.4'
  body-lg:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '400'
    lineHeight: '1.6'
  body-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: '1.5'
  body-sm:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '400'
    lineHeight: '1.5'
  body-emphasis:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '600'
    lineHeight: '1.5'
  label-lg:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '600'
    lineHeight: '1.2'
    letterSpacing: 0.01em
  label-sm:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '500'
    lineHeight: '1.2'
  headline-lg-mobile:
    fontFamily: Space Grotesk
    fontSize: 28px
    fontWeight: '500'
    lineHeight: '1.2'
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  unit: 4px
  xs: 4px
  sm: 8px
  md: 16px
  lg: 24px
  xl: 32px
  gutter: 16px
  margin-mobile: 16px
  margin-desktop: 24px
---

## Brand & Style

The design system is built upon a **Corporate / Modern** foundation with a distinct **Human-Centric** overlay. It is designed to evoke a sense of protection, sincerity, and clarity—positioning the product as a reliable guardian that is approachable rather than institutional. The visual language avoids dramatic or "victim-centric" tropes, opting instead for an empowering and clean aesthetic that resonates with a broad age demographic (ages 11 to 21+).

The style is characterized by:
- **Breathable Layouts:** High use of whitespace (using the "Cold Gray" base) to prevent visual density.
- **Flat Visual Language:** A strictly 2D approach with no gradients or heavy shadows, emphasizing transparency and honesty.
- **Supportive Connectivity:** The use of line illustrations and geometric shapes that imply "hand-holding" or "unity" without being overly sentimental.
- **Professional Warmth:** Balancing the technical stability of slate blue with the energetic, welcoming pop of amber.

## Colors

The palette follows a **60-25-10-5** distribution rule to maintain visual hierarchy and ensure the "Amber" accent remains impactful through scarcity.

- **Surface Strategy:** The primary background is "Cold Gray" (`#F4F6F8`). Pure White (`#FFFFFF`) is reserved strictly for nested elements that need to pop off the background, such as cards or form fields.
- **Primary Blue:** Used for brand identity, headers, and primary actions. It represents stability.
- **Amber Accent:** Used sparingly for badges and "featured" indicators. **Contrast Warning:** Never use white text on Amber; always use the dark neutral (`#2C3540`) for legibility.
- **Functional (Semantic):** Success Green and Error Red are used strictly for status feedback and are never used decoratively.

## Typography

The system utilizes a dual-font strategy to balance character with utility. 

- **Headlines:** Space Grotesk provides a geometric, confident personality. All headings must use **Sentence case**; avoid All-Caps to maintain a friendly, approachable tone.
- **Body:** Inter is used for all long-form content and UI labels to ensure maximum readability across devices. 
- **Hierarchy:** Use weight (SemiBold 600) rather than color shifts for emphasis within body text. 
- **Scaling:** On mobile devices, large headlines should scale down to 28px to maintain visual balance within the grid.

## Layout & Spacing

This design system uses a **Fluid Grid** model based on an 8px rhythmic scale.

- **Grid:** A 12-column grid for desktop and a 4-column grid for mobile.
- **Gutters:** Standardized at 16px to maintain "breathing room" between content blocks.
- **Margins:** Page-level margins are set to 16px on mobile and 24px on desktop to frame the content.
- **Component Spacing:** Use the `md` (16px) unit for the space between internal card elements, and `sm` (8px) for related label/input pairs.

## Elevation & Depth

The design system follows an **Outlined Minimalist** philosophy. Depth is created through tonal layering rather than traditional shadows.

- **Tonal Layers:** The background is `#F4F6F8`. Primary interactive containers (cards) use a `#FFFFFF` fill to sit "above" the surface.
- **Borders:** Use low-contrast outlines (`#D5DAE0`) with a thin 1px width to define boundaries. 
- **Shadows:** Avoid drop shadows. If necessary for extreme focus (e.g., a modal), use a very soft, diffused ambient shadow with low opacity (0.05) and no spread.
- **Mass Rule:** Avoid heavy color masses. Use thin-stroke lines and "hollow" shapes to keep the UI light and airy.

## Shapes

The shape language is organic and soft, avoiding harsh 90-degree corners to reinforce the "Sincere" brand personality.

- **Primary Radius:** Components like cards use a 12px (`rounded-lg`) radius.
- **Secondary Radius:** Interactive elements like buttons and input fields use an 8px (`rounded-md`) radius.
- **Illustration Style:** All custom line art must use **Rounded Terminals** for strokes. Path junctions should be organic and curved, mirroring the "liquid" or "eye-like" geometry found in the logo assets.

## Components

### Buttons
- **Primary:** Solid Blue (`#3D6B99`) with White text. 8px corner radius.
- **Secondary:** Transparent background with a 1px Blue border and Blue text.
- **States:** Active/Pressed states for primary buttons should shift to the Darker Blue (`#2C4F73`).

### Cards
- **Standard:** White fill, 12px radius, and a subtle `#D5DAE0` border.
- **Featured:** Use a soft Amber background (`#FDF0DC`) with a 1px Amber border to highlight specific content.

### Inputs
- **Fields:** White fill, 1px `#D5DAE0` border, 8px radius. Placeholder text uses `#939CA6`.
- **Focus State:** Border color shifts to Primary Blue with a 1px stroke increase.

### Badges/Chips
- **Role Badges:** Specifically for Student/Parent/Teacher roles. Use Amber Surface (`#FDF0DC`) with Dark Neutral text.
- **Status Chips:** Use semantic green/red backgrounds at 10% opacity with full-saturation text for high legibility.

### Line Illustrations
- **Style:** Flat, mono-weight lines. Use the Primary Blue or Dark Neutral for outlines.
- **Fills:** Use Amber or Light Blue sparingly as "pops" of color within the line work. 
- **Content:** Always depict human figures in positions of strength, togetherness, or offering support.