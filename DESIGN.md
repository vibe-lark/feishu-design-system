# Lark CSS Specification (Inspired by Universe Design)

This document provides a consolidated guide to the Lark CSS requirements for designers and developers. It is heavily inspired by and references the official Universe Design (UD) style guide, adapted specifically for defining and adjusting Lark's CSS architecture.

---

# 1. Icon

## 1.1. Terminology

*   **System Icon**: A graphic symbol with a clear, specific meaning, representing a common action, object, or status. Its core goal is to guide interaction and improve information retrieval efficiency.
*   **Line Icon**: An icon where lines are the primary visual form. This clean, modern style is the mainstream choice for Lark.
*   **Filled Icon**: An icon primarily using solid color fills. It has a stronger visual weight and is often used to indicate a selected or active state.
*   **Pixel Snapping**: To ensure icons are sharp and clear on screen, their key structures (especially vertical and horizontal edges) must be precisely aligned to the pixel grid.

## 1.2. Usage Scenarios

*   **Navigation Icons**: Located in primary navigation areas like sidebars and tab bars for global feature switching. They have the highest hierarchical importance.
*   **Action Icons**: Placed within buttons, toolbars, and list items to trigger specific operations like "Edit," "Delete," or "Refresh."
*   **Semantic Icons**: Used with text to convey status or identify types, such as for warnings, success states, or document formats, enhancing information readability.

## 1.3. Key Specifications

*   **Design Principles**: Accuracy (clear, unambiguous meaning), Simplicity (no unnecessary decoration), Consistency (uniform style, corner radii, and lines), and Pleasantness (elegant details).
*   **Base Grid**: All icons are designed within a `24x24` canvas, maintaining a `2px` safe margin, with the actual content drawn in a `20x20` area.
*   **Line Weight**: Standard icons use a `1.5px` stroke width. Micro-icons (e.g., `12px` or `14px`) may use a `1px` stroke width.
*   **Corner Radius**: Outer contours and large curves use a `2px` radius; internal details and small curves use a `1px` radius. Line caps are rounded.
*   **Color**: Icon color defaults to inheriting the parent's text color (`currentColor`). Semantic icons (e.g., Success, Warning, Danger) use their corresponding functional colors. Document-type icons have a separate multi-color palette.
*   **Naming Convention**: Follows a `category_name_style_size` format, such as `business_add-friends_line_16`.

## 1.4. Common Mistakes

*   **Ambiguous Meaning**: Using overly abstract or multi-interpretational graphics, e.g., using a "heart" for "favorite" (which can be confused with "like"). Use conventional symbols, like a "star" for "favorite."
*   **Over-decoration**: Adding unnecessary details that become hard to recognize at small sizes. Icons should remain simple.
*   **Inconsistent Style**: Mixing different design styles (e.g., line and filled), corner radii, or line weights within the same product.
*   **Pixel Blurring**: Failure to align to the pixel grid, causing icon edges to appear blurry, especially on lower-resolution displays.

## 1.5. Metrics & Examples

*   **Size Scale**: A standard size scale is provided: `12px`, `14px`, `16px`, `20px`, `24px`, `32px`, `40px`. The default icon size is `16px`.
*   **Arrowhead Definition**: The apex angle of all directional arrowheads is consistently `60°`.
*   **Disabled Style**: The disabled state for an icon is indicated by reducing its opacity to `30%`, not by filling it with gray.
*   **Line/Fill Combination**: Line icons are used for the default state, while Filled icons are used for hover or active states to create clear differentiation.

---

# 2. Layout

## 2.1. Terminology

*   **Grid System**: A layout tool that divides the page into equal-width columns (typically 24) to ensure consistent alignment and rhythm.
*   **Spacing Unit**: A set of standard values for controlling margins and paddings. Lark uses a 4px base unit, inherited from UD principles.
*   **Content Area**: The primary region of the page for information and interaction, with a width that adjusts responsively.
*   **Responsive Layout**: A layout that automatically adjusts its arrangement based on screen size (breakpoints) to provide an optimal viewing experience.

## 2.2. Usage Scenarios

*   **Enterprise Applications**: Often use a classic "top-nav/sidebar/content" structure for clear functional division.
*   **Dashboards**: Use a card-based layout to aggregate different data modules or functional entry points on a single page for a quick overview.
*   **Content Pages**: Use a single or dual-column layout to display articles or documents, with the main column for content and a side column for navigation or related information.

## 2.3. Key Specifications

*   **Base Spacing**: Based on a 4px unit, creating a standard scale: `4px, 8px, 12px, 16px, 24px, 32px, 48px`. All component and block spacing must adhere to this scale.
*   **Grid Columns**: A 24-column grid system enables flexible column combinations.
*   **Common Patterns**:
    *   **Side-by-side**: Sidebar navigation + main content area.
    *   **Top-down**: Global top navigation + content area below.
*   **Content Width**: On desktops, the main content area is typically capped at a `1200px` max-width to ensure readability on wide screens.

## 2.4. Common Mistakes

*   **Custom Spacing**: Using non-standard values like `10px` or `15px`, which disrupts the visual rhythm.
*   **Misalignment**: Elements not aligned to the grid, creating a sense of visual disorder.
*   **Imbalanced Density**: Overusing whitespace in data-heavy enterprise apps, wasting screen real estate; or, conversely, cramming too much into content pages, creating a cluttered feel.
*   **Ignoring Responsiveness**: Poor layout performance on small screens, leading to horizontal scrolling or text overflow.

## 2.5. Metrics & Examples

*   **Standard Breakpoints**:
    *   `<576px` (Extra Small)
    *   `≥576px` (Small)
    *   `≥768px` (Medium)
    *   `≥992px` (Large)
    *   `≥1200px` (Extra Large)
*   **Page Padding**: Content areas typically have `24px` or `32px` of padding on the sides.
*   **Card Gutter**: The space between cards is usually `16px` or `24px`.

---

# 3. Typography

## 3.1. Font Family

Font stacks are defined by locale to ensure optimal rendering across platforms and languages.

### Chinese Locale

```css
font-family: LarkHackSafariFont, LarkEmojiFont, LarkChineseQuote, -apple-system, BlinkMacSystemFont, Helvetica Neue, Tahoma, PingFang SC, Microsoft Yahei, Arial, Hiragino Sans GB, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
```

### English Locale

```css
font-family: LarkHackSafariFont, LarkEmojiFont, -apple-system, BlinkMacSystemFont, Helvetica Neue, Tahoma, PingFang SC, Microsoft Yahei, Arial, Hiragino Sans GB, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
```

### Japanese Locale

```css
font-family: LarkHackSafariFont, LarkEmojiFont, "ヒラギノ角ゴシック", "Hiragino Sans", "Yu Gothic UI", "Microsoft Jhenghei UI", "Microsoft Yahei UI", "ＭＳ Ｐゴシック", "PingFang SC", "Hiragino Sans GB", Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
```

## 3.2. Type Scale

A clear type hierarchy distinguishes primary and secondary content, creating visual order.

### PC Type Scale

| Role | Size | Line Height | Weight |
| :--- | :--- | :--- | :--- |
| Extra Large Title | 30px | 46px | Semibold |
| H1 Title | 24px | 36px | Semibold |
| H2 Title | 20px | 30px | Medium |
| H3 Title | 18px | 28px | Medium |
| H4 Title | 16px | 24px | Medium |
| H5 Title | 16px | 24px | Regular |
| Supporting Title | 14px | 22px | Medium |
| Body | 14px | 22px | Regular |
| Supporting Body | 12px | 20px | Regular |
| Auxiliary | 12px | 20px | Medium |
| Small Auxiliary | 10px | 16px | Medium |
| Minimum Auxiliary | 10px | 16px | Regular |

### Mobile Type Scale (1x)

| Role | Size | Line Height | Weight |
| :--- | :--- | :--- | :--- |
| Extra Large Title | 26px | 40px | Semibold |
| H1 Title | 24px | 36px | Semibold |
| H2 Title | 20px | 30px | Medium |
| H3 Title | 17px | 26px | Medium |
| H4 Title | 17px | 26px | Regular |
| Supporting Title | 16px | 24px | Medium |
| Body | 16px | 24px | Regular |
| Large Supporting Body | 14px | 22px | Medium |
| Supporting Body | 14px | 22px | Regular |
| Auxiliary | 12px | 20px | Medium |
| Small Auxiliary | 12px | 20px | Regular |
| Extra Small Auxiliary | 10px | 16px | Medium |
| Minimum Auxiliary | 10px | 16px | Regular |

---

# 4. Color

The Lark color system is built on a foundation of CSS custom properties (variables) to ensure consistency and support themes like Light and Dark mode, aligning with Universe Design guidelines.

## 4.1. Brand Color

The Lark brand blue, **B500 (`#3370FF`)**, is the single, primary emphasis color. It conveys efficiency, intelligence, and calmness.

*   **Usage**: It should be used for primary calls-to-action (CTAs), selected states, information highlights, and, where appropriate, as an accent in illustrations.

## 4.2. Grayscale

A neutral grayscale palette is used for text, backgrounds, and borders to create a clear information hierarchy.

| Token | Hex | Recommended Usage |
| :---- | :------ | :---------------- |
| N900 | `#0F1114` | Primary titles, main body text. |
| N600 | `#646A73` | Secondary body text. |
| N500 | `#8F959E` | Subtitles, placeholders, helper text. |
| N400 | `#BBBFC4` | Disabled text and elements. |

## 4.3. Functional Colors

Functional colors represent clear states and information, such as success, warnings, errors, and links. Their use should be consistent across all products.

| Color | Hex | Contrast Ratio (CCA) |
| :---- | :------ | :--- |
| Blue | `#3370FF` | 4.3:1 |
| Green | `#34C724` | 9.3:1 |
| Yellow | `#FFC60A` | 13.3:1 |
| Red | `#F54A45` | 3.5:1 |
| Orange | `#FF8800` | 8.8:1 |

## 4.4. Implementation

**Rule**: Never hard-code color values. Always use CSS custom properties defined at the project or system level. This ensures that all colors can be centrally managed and themed.

For example, instead of writing `color: #3370FF;`, use a variable:

```css
.my-component {
  /* Example: project-level CSS custom property */
  color: var(--ud-color-brand-b500);
}
```

---

# 5. Style / Border Radius

Style refers to the foundational visual elements that define component appearance, such as corner radii and borders.

## 5.1. Border Radius

A strict and consistent border-radius hierarchy is enforced to create a unified visual language.

| Radius | Usage |
| :--- | :--- |
| **3px** | Small, interactive components (e.g., Buttons, Inputs, Tags). |
| **6px** | Medium-sized components (e.g., Dropdown menus, Tree nodes). |
| **12px** | Large containers (e.g., Cards, Modals, Popovers). |
| **Circle** | Circular elements (e.g., Avatars, Badges). |
| **Full** | Pill-shaped elements (e.g., Toggles). |

## 5.2. Borders & Surfaces

*   **Flat Cards**: Standard cards are flat and do not use shadows. They rely on a `1px` border to create separation from the background.
*   **Filled Inputs**: Input fields use a background fill to define their boundary, not a visible border in their default state. A border only appears on focus.

---

# 6. Motion

Motion design in Lark is functional, restrained, and efficient, reflecting UD principles. Animations should serve the interaction by providing smooth feedback and clear transitions, not by being purely decorative.

## 6.1. Principles

*   **Purposeful**: Animations should be natural, fast, and meaningful. Avoid long, complex, or irrelevant animations that distract the user.
*   **Performant**: Prioritize animating CSS properties that are cheap to render, such as `transform` and `opacity`. Avoid properties like `width`, `height`, or `margin` that can cause performance issues.

## 6.2. Easing & Duration

*   **Easing**:
    *   **Ease-out**: Use for elements entering the screen (e.g., modals, dropdowns). This feels responsive.
    *   **Ease-in**: Use for elements exiting the screen.
*   **Duration**:
    *   **100ms**: For micro-interactions like color or background changes on hover.
    *   **200-300ms**: For most component transitions, like expanding/collapsing panels.
    *   **>300ms**: Reserved for larger, more complex scene transitions.

---

# 7. Elevation

Elevation refers to the Z-axis depth that creates a sense of hierarchy. In Lark, elevation is used conservatively and is primarily achieved through box shadows, adopting the UD elevation model. It is defined by a clear, two-tier model.

## 7.1. Elevation Tiers

*   **Page Level (Flat)**: This is the base layer containing all static, non-floating page content like cards, inputs, and tables. **Elements at this level do not have shadows.** They use borders or background colors for separation.

*   **Floating Level (Elevated)**: This layer sits above the page level and contains all temporary, overlaying UI elements. **Shadows are used exclusively for these elements** to visually lift them off the page.
    *   **Usage**: Modals, Dialogs, Dropdowns, Popovers, and Toasts.

## 7.2. Shadow Style

A single, unified shadow style is applied to all floating-level elements to ensure consistency across Lark applications. The shadow values differ for light and dark modes but are managed by the same design token.

*   **Light Mode Shadow**: `box-shadow: 0 0 1px rgba(0,0,0,0.3), 0 4px 14px rgba(0,0,0,0.1);`
*   **Dark Mode Shadow**: `box-shadow: inset 0 0 0 1px rgba(255,255,255,0.1), 0 4px 14px rgba(0,0,0,0.25);`
