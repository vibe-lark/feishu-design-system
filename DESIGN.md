# Design System: Feishu (Semi Design)

## 1. Visual Theme & Atmosphere

Feishu's design system — Semi Design — is a modern, professional, and flexible enterprise interface framework. Born from ByteDance's internal collaboration suite (Feishu/Lark), it radiates pragmatic neutrality: clean lines, balanced information density, and highly accessible surfaces designed to serve complex B2B workflows without visual fatigue. This is not decorative minimalism — it's engineered efficiency.

The system's defining trait is its **CSS variable-first architecture**. Every color, every surface, every state is expressed as a `var(--semi-color-*)` token, enabling seamless Light/Dark mode switching with zero code changes. The color philosophy leans on a saturated brand blue (`#0064FA`) as the singular accent, with a carefully calibrated neutral gray scale built on rgba overlays rather than static hex values. This means backgrounds, borders, and fills share the same base hue but shift opacity — creating surfaces that feel _related_ rather than disparate.

Semi Design's component styling uses **filled inputs** (background-based rather than bordered), a tight **3px–6px–12px border-radius hierarchy**, and subtle **1px shadow-borders** for elevation. The result is an interface that feels solid and grounded — cards don't float, buttons don't pop — everything sits comfortably in its layer.

**Key Characteristics:**
- CSS variable-first: Never hardcode hex values — always use `var(--semi-color-*)` for automatic Light/Dark mode
- Inter font family with system fallbacks including PingFang SC and Microsoft YaHei for CJK support
- Brand blue primary (`#0064FA` Light / `#54A9FF` Dark) as the single accent color
- Filled input paradigm: inputs use background fills (`rgba(46,50,56,0.05)`) rather than visible borders
- Strict 3px → 6px → 12px → full border-radius hierarchy for visual consistency
- rgba-based neutral scale: fills, borders, and text share the same gray base with varying opacity
- AI-specific gradient colors for AI-powered feature interfaces
- 3000+ design tokens available via Semi DSM for full customization
- Enterprise-grade: A11y-compliant, i18n-ready (dozens of languages), RTL-supported

## 2. Color Palette & Roles

### Semantic Colors (Light / Dark)

| Name | CSS Variable | Light | Dark | Role |
|------|-------------|-------|------|------|
| **Primary** | `var(--semi-color-primary)` | `#0064FA` | `#54A9FF` | CTAs, active states, key interactive elements |
| **Secondary** | `var(--semi-color-secondary)` | `#0095EE` | `#40B4F3` | Supporting actions, secondary highlights |
| **Tertiary** | `var(--semi-color-tertiary)` | `#6B7075` | `#888D92` | Third-level actions, neutral icons |
| **Success** | `var(--semi-color-success)` | `#3BB346` | `#5DC264` | Success messages, safe actions |
| **Warning** | `var(--semi-color-warning)` | `#FC8800` | `#FFAE43` | Warning states, alerts |
| **Danger** | `var(--semi-color-danger)` | `#F93920` | `#FC725A` | Error states, destructive actions |
| **Info** | `var(--semi-color-info)` | `#0064FA` | `#54A9FF` | Informational messages (same hue as Primary) |

### Backgrounds & Surfaces (Light / Dark)

| Name | CSS Variable | Light | Dark | Role |
|------|-------------|-------|------|------|
| **Page Background** | `var(--semi-color-bg-0)` | `#FFFFFF` | `#16161A` | Lowest level background |
| **Elevated Surface** | `var(--semi-color-bg-1)` | `#FFFFFF` | `#232429` | Cards, containers |
| **Modal Surface** | `var(--semi-color-bg-2)` | `#FFFFFF` | `#35363C` | Modals, popovers |
| **Fill Default** | `var(--semi-color-fill-0)` | `rgba(46,50,56,0.05)` | `rgba(255,255,255,0.12)` | Component backgrounds (inputs) |
| **Fill Hover** | `var(--semi-color-fill-1)` | `rgba(46,50,56,0.09)` | `rgba(255,255,255,0.16)` | Component hover backgrounds |
| **Fill Active** | `var(--semi-color-fill-2)` | `rgba(46,50,56,0.13)` | `rgba(255,255,255,0.20)` | Component active/pressed backgrounds |

### Text & Borders (Light / Dark)

| Name | CSS Variable | Light | Dark | Role |
|------|-------------|-------|------|------|
| **Primary Text** | `var(--semi-color-text-0)` | `#1C1F23` | `#F9F9F9` | Main content text |
| **Secondary Text** | `var(--semi-color-text-1)` | `rgba(28,31,35,0.8)` | `rgba(249,249,249,0.8)` | Descriptions, secondary content |
| **Tertiary Text** | `var(--semi-color-text-2)` | `rgba(28,31,35,0.62)` | `rgba(249,249,249,0.6)` | Placeholder, disabled-like text |
| **Border** | `var(--semi-color-border)` | `rgba(28,31,35,0.08)` | `rgba(255,255,255,0.08)` | Default borders and dividers |

### Disabled States (Light / Dark)

| Name | CSS Variable | Light | Dark |
|------|-------------|-------|------|
| **Disabled Background** | `var(--semi-color-disabled-bg)` | `#E6E8EA` | `#2E3238` |
| **Disabled Text** | `var(--semi-color-disabled-text)` | `rgba(28,31,35,0.35)` | `rgba(249,249,249,0.35)` |
| **Disabled Border** | `var(--semi-color-disabled-border)` | `#E6E8EA` | `#2E3238` |

### AI Colors

Semi Design provides dedicated AI-themed color variables for AI-powered features:

| Name | CSS Variable | Description |
|------|-------------|-------------|
| **AI General** | `var(--semi-color-ai-general)` | Multi-stop linear gradient (blue → purple → pink) for AI accents |
| **AI Purple** | `var(--semi-color-ai-purple)` | Solid purple accent (`rgba(166,71,255)` Light / `rgba(195,117,255)` Dark) |
| **AI Background Bottom** | `var(--semi-color-ai-background-bottom)` | Subtle gradient overlay for AI section backgrounds |
| **AI Background Top** | `var(--semi-color-ai-background-top)` | Stronger gradient overlay for AI section top layers |

Each AI color supports `-hover`, `-active`, and `-disabled` state variants.

### Data Visualization Palette

20 data colors (`var(--semi-color-data-0)` through `var(--semi-color-data-19)`) optimized for charts. Designed to be distinguishable and accessible in both Light and Dark modes. Use with VChart or any charting library.

## 3. Typography Rules

### Font Family
- **Primary**: `"Inter", -apple-system, BlinkMacSystemFont, "Segoe UI", "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", "Helvetica Neue", Helvetica, Arial, sans-serif`
- All text (headlines, body, labels) uses the same font stack — no secondary display font.

### Hierarchy

| Role | Size | Weight | Line Height | Letter Spacing | Notes |
|------|------|--------|-------------|----------------|-------|
| H1 | 32px | 600 | 44px | normal | Page titles, hero headings |
| H2 | 28px | 600 | 40px | normal | Section headings |
| H3 | 24px | 600 | 32px | normal | Sub-section headings |
| H4 | 20px | 600 | 28px | normal | Card titles, panel headers |
| H5 | 18px | 600 | 24px | normal | Sub-headings |
| H6 | 16px | 600 | 22px | normal | Small headings |
| Body | 14px | 400 | 20px | normal | Standard reading text |
| Body Small | 12px | 400 | 16px | normal | Labels, secondary text, captions |

### Principles
- **One font stack, full hierarchy**: Semi achieves visual hierarchy through size and weight alone — no mixing of font families.
- **CJK-optimized fallbacks**: PingFang SC, Hiragino Sans GB, and Microsoft YaHei ensure beautiful Chinese/Japanese/Korean rendering across all platforms.
- **Two weights, strict roles**: 400 (regular) for body/reading, 600 (semibold) for headings/emphasis. This narrow range creates clean, scannable enterprise interfaces.
- **Text color hierarchy**: Primary (`--semi-color-text-0`) → Secondary (`--semi-color-text-1`) → Tertiary (`--semi-color-text-2`) → Disabled (`--semi-color-text-3`). Never skip levels.

## 4. Component Stylings

### Border Radius Hierarchy

| Token | Value | Use Cases |
|-------|-------|-----------|
| `--semi-border-radius-extra-small` | 3px | Inner elements (checkbox ticks) |
| `--semi-border-radius-small` | 3px | Buttons, Inputs, Tags, Tabs |
| `--semi-border-radius-medium` | 6px | Dropdowns, Select menus, Tree nodes |
| `--semi-border-radius-large` | 12px | Modals, Cards, Popovers |
| `--semi-border-radius-circle` | 50% | Avatars, Badges |
| `--semi-border-radius-full` | 9999px | Pill-shaped elements |

### Buttons

| Variant | Background | Text | Radius | Use |
|---------|-----------|------|--------|-----|
| **Primary** | `var(--semi-color-primary)` | White | 3px | Main CTA actions |
| **Secondary** | `var(--semi-color-secondary)` | White | 3px | Supporting actions |
| **Tertiary** | Transparent → `var(--semi-color-fill-0)` on hover | Text color | 3px | Low-emphasis actions |
| **Danger** | `var(--semi-color-danger)` | White | 3px | Destructive actions |
| **Warning** | `var(--semi-color-warning)` | White | 3px | Caution actions |

### Cards & Containers
- Background: `var(--semi-color-bg-1)` (Light: `#FFFFFF` / Dark: `#232429`)
- Border: `1px solid var(--semi-color-border)`
- Radius: `var(--semi-border-radius-large)` (12px)
- Standard cards are flat with borders; no shadow by default

### Modals & Popovers
- Background: `var(--semi-color-bg-2)` (Light: `#FFFFFF` / Dark: `#35363C`)
- Radius: `var(--semi-border-radius-large)` (12px)
- Shadow (Light): `0 0 1px rgba(0,0,0,0.3), 0 4px 14px rgba(0,0,0,0.1)`
- Shadow (Dark): `inset 0 0 0 1px rgba(255,255,255,0.1), 0 4px 14px rgba(0,0,0,0.25)`

### Forms & Inputs
- **Default height**: 32px (Small: 24px, Large: 40px)
- **Background**: `var(--semi-color-fill-0)` — filled style, no visible border
- **Border**: Transparent by default
- **Radius**: 3px (`--semi-border-radius-small`)
- **Hover**: Background → `var(--semi-color-fill-1)`
- **Focus**: Background → `var(--semi-color-fill-0)`, plus `1px solid var(--semi-color-focus-border)` (Primary blue)
- **Error**: Red asterisk via `var(--semi-color-danger)` for required fields

### Tables
- Header background: `var(--semi-color-bg-1)`
- Row dividers: `var(--semi-color-border)`
- Row hover: `var(--semi-color-fill-0)`
- Striped rows optional

### Tabs
- **Line tabs**: 2px bottom border in `var(--semi-color-primary)` for active state
- **Card tabs**: `var(--semi-border-radius-small)` on top corners

### Tags & Badges
- Tags: `var(--semi-border-radius-small)` (3px)
- Badges/Avatars: Fully rounded (`--semi-border-radius-circle`)

### Iconography
- Default size: 16px (`--semi-icon-size-medium`)
- Size scale: 8px, 12px, 16px, 20px, 24px
- Color: inherits `currentColor` or uses `var(--semi-color-text-2)` for neutral/secondary

## 5. Layout Principles

### Spacing Scale
Semi Design uses a 4px base unit:
- **Scale**: 4px, 8px, 12px, 16px, 24px
- All margins and paddings should align to this scale for consistent rhythm.

### Grid & Container
- Standard content width: responsive, typically 1200px max for dashboard layouts
- Sidebar + content pattern for enterprise apps
- 24-column grid system available via `<Row>` and `<Col>` components

### Whitespace Philosophy
- **Balanced density**: Enterprise interfaces need to show information without overwhelming — Semi strikes the balance between airy consumer apps and data-dense dashboards.
- **Consistent spacing**: The 4px base unit ensures all elements align to the same invisible grid.
- **Breathing room**: Cards and sections use 16px–24px internal padding; section gaps of 24px–32px.

## 6. Depth & Elevation

| Level | Treatment | Use |
|-------|-----------|-----|
| **Flat (Level 0)** | No shadow, optional 1px border | Standard cards, containers, inputs |
| **Elevated (Level 1)** | `0 0 1px rgba(0,0,0,0.3), 0 4px 14px rgba(0,0,0,0.1)` (Light) | Modals, popovers, toasts, dropdowns |
| **Elevated (Level 1 Dark)** | `inset 0 0 0 1px rgba(255,255,255,0.1), 0 4px 14px rgba(0,0,0,0.25)` | Dark mode floating elements |

**Shadow Philosophy**: Semi Design takes a conservative approach to elevation. Standard page elements (cards, containers) remain flat, relying on 1px borders and subtle background color variations (`--semi-color-fill-0`) for hierarchy. Shadows are reserved exclusively for floating elements (modals, popovers, toasts) — creating a clear two-layer system: the page surface and the overlay layer.

## 7. Do's and Don'ts

### Do
- **Always use CSS Variables**: Use `var(--semi-color-*)` for all colors — never hardcode hex values. This is the #1 rule for Dark Mode compatibility.
- Use the primary blue (`var(--semi-color-primary)`) consistently for the single most important action on screen.
- Maintain the strict border-radius hierarchy: 3px for basic controls, 6px for menus/dropdowns, 12px for large containers.
- Use semantic colors (Success, Warning, Danger) strictly for their feedback roles — not for decoration.
- Follow the 4px spacing scale (4px, 8px, 12px, 16px, 24px) for all margins and paddings.
- Use the filled input pattern — inputs have background fills, not visible borders in default state.
- Leverage the text color hierarchy (`text-0` → `text-1` → `text-2` → `text-3`) to create information layers.
- Use AI color tokens (`--semi-color-ai-*`) for AI-related features and interfaces.

### Don't
- Don't mix different font families — rely on Inter and the native system font stack.
- Don't use shadows on standard cards or containers — shadows are reserved for floating elements only.
- Don't skip text color hierarchy levels (e.g., don't use `text-2` for primary content).
- Don't use border-radius values outside the defined scale (3px, 6px, 12px, circle, full).
- Don't apply semantic colors (success green, danger red) for decorative purposes.
- Don't use traditional visible borders on inputs in their default state — use the filled background pattern.
- Don't hardcode Light or Dark mode values — always use the CSS variable to let the system handle mode switching.
- Don't create custom gray values — use the rgba-based fill system (`fill-0`, `fill-1`, `fill-2`) for all neutral backgrounds.

## 8. Responsive Behavior

### Breakpoints

| Name | Width | Key Changes |
|------|-------|-------------|
| Extra Small | <576px | Single column, stacked layout |
| Small | ≥576px | Two-column starts |
| Medium | ≥768px | Standard tablet layout |
| Large | ≥992px | Desktop layout begins |
| Extra Large | ≥1200px | Full desktop, max content width |
| XXL | ≥1600px | Wide desktop, generous margins |

### Touch Targets
- Default control height: 32px for standard, 40px for large (comfortable touch targets)
- Buttons have adequate padding (8px–16px vertical minimum)
- Mobile-first: all interactive elements meet 44px minimum touch target on mobile

### Collapsing Strategy
- Navigation: sidebar collapses to icon-only or hamburger menu
- Tables: horizontal scroll or card-based layout on mobile
- Forms: full-width stacked layout on small screens
- Cards: multi-column → single column stacked
- Modals: full-screen on mobile, centered dialog on desktop

## 9. Agent Prompt Guide

### Quick Color Reference
- Primary CTA: `var(--semi-color-primary)` → `#0064FA` (Light) / `#54A9FF` (Dark)
- Page background: `var(--semi-color-bg-0)` → `#FFFFFF` (Light) / `#16161A` (Dark)
- Card surface: `var(--semi-color-bg-1)` → `#FFFFFF` (Light) / `#232429` (Dark)
- Primary text: `var(--semi-color-text-0)` → `#1C1F23` (Light) / `#F9F9F9` (Dark)
- Secondary text: `var(--semi-color-text-1)` → `rgba(28,31,35,0.8)` (Light)
- Input fill: `var(--semi-color-fill-0)` → `rgba(46,50,56,0.05)` (Light) / `rgba(255,255,255,0.12)` (Dark)
- Border: `var(--semi-color-border)` → `rgba(28,31,35,0.08)` (Light) / `rgba(255,255,255,0.08)` (Dark)

### Example Component Prompts
- "Create a hero section on white background. Headline at 32px Inter weight 600, line-height 44px, color var(--semi-color-text-0). Subtitle at 14px weight 400, line-height 20px, color var(--semi-color-text-1). Primary CTA button (var(--semi-color-primary), 3px radius, 8px 16px padding, white text) and secondary button (transparent bg, text color, var(--semi-color-fill-0) on hover, 3px radius)."
- "Design a card: var(--semi-color-bg-1) background, 1px border var(--semi-color-border), 12px radius. Title at 20px Inter weight 600. Body at 14px weight 400, var(--semi-color-text-1). No shadow — flat card."
- "Build a form input: var(--semi-color-fill-0) background, no visible border, 3px radius, 32px height, 14px Inter text. On hover: var(--semi-color-fill-1). On focus: 1px solid var(--semi-color-primary) border, var(--semi-color-fill-0) background."
- "Create a data table: var(--semi-color-bg-1) header background, var(--semi-color-border) row dividers, var(--semi-color-fill-0) row hover. 14px body text, 12px column headers in var(--semi-color-text-2)."
- "Design a modal: var(--semi-color-bg-2) background, 12px radius, shadow 0 0 1px rgba(0,0,0,0.3) + 0 4px 14px rgba(0,0,0,0.1). Title at 20px weight 600, body at 14px. Primary action button and tertiary cancel button."
- "Build a tab navigation: line-style tabs with 2px bottom border in var(--semi-color-primary) for active tab. Inactive tabs in var(--semi-color-text-2). 14px Inter weight 500 for labels."

### Iteration Guide
1. Always start with CSS variables — `var(--semi-color-primary)` not `#0064FA`
2. Inputs are filled (background-based), not bordered in default state
3. Two weights only: 400 (body/reading) and 600 (headings/emphasis)
4. Border-radius is strict: 3px (controls) → 6px (menus) → 12px (containers) → circle (avatars)
5. Shadows only on floating elements (modals, popovers, dropdowns) — cards are flat
6. Text hierarchy: `text-0` → `text-1` → `text-2` → `text-3` — never skip levels
7. The fill system (`fill-0` → `fill-1` → `fill-2`) handles all neutral interactive backgrounds
8. For AI features, use `--semi-color-ai-*` tokens for gradient and purple accents
