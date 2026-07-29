---
name: Akranca Community System
colors:
  surface: '#FFFFFF'
  surface-dim: '#d2dbe9'
  surface-bright: '#f8f9ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#eef4ff'
  surface-container: '#e5effd'
  surface-container-high: '#e0e9f7'
  surface-container-highest: '#dae3f2'
  on-surface: '#131c26'
  on-surface-variant: '#42474f'
  inverse-surface: '#28313c'
  inverse-on-surface: '#e9f1ff'
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
  tertiary: '#6c4a00'
  on-tertiary: '#ffffff'
  tertiary-container: '#886116'
  on-tertiary-container: '#ffe4bf'
  error: '#ba1a1a'
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
  tertiary-fixed: '#ffdeac'
  tertiary-fixed-dim: '#f1be6b'
  on-tertiary-fixed: '#281900'
  on-tertiary-fixed-variant: '#604100'
  background: '#F4F6F8'
  on-background: '#131c26'
  surface-variant: '#dae3f2'
  muted-text: '#707D83'
typography:
  headline-xl:
    fontFamily: Space Grotesk
    fontSize: 48px
    fontWeight: '500'
    lineHeight: 56px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Space Grotesk
    fontSize: 32px
    fontWeight: '500'
    lineHeight: 40px
  headline-lg-mobile:
    fontFamily: Space Grotesk
    fontSize: 28px
    fontWeight: '500'
    lineHeight: 36px
  headline-md:
    fontFamily: Space Grotesk
    fontSize: 24px
    fontWeight: '500'
    lineHeight: 32px
  body-lg:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '400'
    lineHeight: 28px
  body-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  label-md:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '600'
    lineHeight: 20px
    letterSpacing: 0.01em
  label-sm:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '500'
    lineHeight: 16px
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  container-max: 1200px
  gutter: 24px
  margin-desktop: 64px
  margin-mobile: 20px
  stack-sm: 8px
  stack-md: 16px
  stack-lg: 32px
  section-padding: 80px
---

## Brand & Style

The design system is crafted for a non-profit community platform dedicated to raising awareness about peer bullying. The brand personality is **authoritative yet empathetic, professional, and secure**. It aims to evoke a sense of solidarity and institutional trust, ensuring users feel they are in a safe, moderated environment.

The design style follows **Modern Corporate Minimalism** with a focus on high-quality photography and structural clarity. It avoids "victimized" tropes, instead using a "faceless framing" approach—focusing on environmental details like corridors, clasped hands, or architectural shadows—to represent the weight of the subject matter without exploiting individuals. A signature navy duotone filter is applied to all primary imagery to maintain visual cohesion and reinforce the brand's serious tone.

## Colors

The palette is dominated by **Navy Blue (#3D6B99)**, which provides a foundation of stability and professional calm. The **Amber (#F0B455)** accent is used strictly for high-priority calls to action or critical warnings, limited to approximately 5% of any given layout to maintain its impact.

The background uses a **Cool Gray (#F4F6F8)** to reduce eye strain and provide a subtle contrast against the **White (#FFFFFF)** surface cards. Text hierarchies are managed through **#2C3540** for primary content and a muted slate gray for secondary metadata.

## Typography

This design system utilizes a high-contrast typographic pairing. **Space Grotesk** is used for all headings to provide a technical, modern edge that distinguishes the platform from traditional, soft-styled non-profits. **Inter** is used for all body text and UI labels to ensure maximum readability and a neutral, functional feel.

All system text is in Turkish. Use "Medium" weights for headlines to maintain authority without appearing aggressive. Body text should prioritize generous line heights (1.5x minimum) to ensure accessibility for users who may be in high-stress situations.

## Layout & Spacing

The layout follows a **Fixed Grid** model on desktop with a 12-column structure and a maximum width of 1200px. On mobile, the system transitions to a single-column fluid layout with 20px side margins.

Spacing is intentionally "airy" to convey a sense of calm. Large section paddings (80px+) are used to separate different thematic areas of the platform, preventing the UI from feeling cluttered or overwhelming. Vertical rhythm is maintained using an 8px base unit.

## Elevation & Depth

Visual hierarchy is achieved through **Tonal Layers** and subtle **Ambient Shadows**. 

- **Level 0 (Background):** The Cool Gray surface serves as the canvas.
- **Level 1 (Cards):** White surfaces with a soft, 10% opacity Navy shadow (Blur: 20px, Y: 4px). This creates a gentle lift that distinguishes interactive content from the background.
- **Level 2 (Modals/Dropdowns):** Higher contrast shadows (Blur: 30px, Y: 8px) with a slight Navy tint to reinforce brand identity in the Z-axis.

Avoid heavy borders; use 1px strokes in a slightly darker gray only when cards are placed on white backgrounds.

## Shapes

The shape language is structured and approachable. 
- **Cards and Containers:** Use a 12px radius (`rounded-lg`) to soften the professional tone.
- **Buttons and Inputs:** Use an 8px radius for a more precise, actionable appearance.
- **Iconography:** Use line-based icons with slightly rounded caps to match the typography's geometric nature.

## Components

### Buttons
- **Primary:** Navy Blue background, White text. 8px radius. Text: "Devam Et", "Gönder".
- **Secondary:** Transparent with Navy Blue 1px border. 
- **Accent/Alert:** Amber background with Dark Text (#2C3540) for high-urgency actions like "Yardım Al".

### Cards
- **Community Card:** 12px radius, White background, subtle shadow. Top section features a Navy duotone image.
- **Information Card:** 12px radius, Navy Blue background with White text for highlighting critical educational content.

### Form Fields
- Labels must be in Inter (Bold) in #2C3540.
- Input fields use White background, 8px radius, and 1px Border in Cool Gray. On focus, the border changes to Navy Blue.
- Placeholder text: "Buraya yazın..."

### Chips
- Used for content categories (e.g., "Siber Zorbalık", "Okul Güvenliği").
- Light Navy background (10% opacity) with Navy text. Pill-shaped (32px radius).

### Lists
- Use generous vertical padding (16px) between items.
- Dividers should be 1px wide in Cool Gray, with 24px horizontal inset to prevent a "boxed-in" feel.