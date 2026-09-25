# Design System & Cloud FinOps Interactive Prototypes

[![Design Tokens](https://img.shields.io/badge/Design%20Tokens-850%2B%20OKLCH-blue)](src/tokens/tokens.css)
[![Figma Parity](https://img.shields.io/badge/Figma-shadcn%2Fui%20Pro%20Blocks-indigo)](docs/FIGMA-COMPONENTS.md)
[![A11y](https://img.shields.io/badge/A11y-WCAG%202.2%20AA-emerald)](.antigravity/rules.md)
[![Pure Vanilla](https://img.shields.io/badge/Stack-Vanilla%20HTML%2FCSS%2FJS-amber)](#architecture--tech-stack)
[![Icons](https://img.shields.io/badge/Icons-FontAwesome%20Pro%207.3.1-black)](src/assets/fontawesome/)

A high-fidelity, production-grade frontend design system and interactive application prototyping workspace. Built strictly with **Vanilla HTML, modern CSS (OKLCH tokens), and lightweight JavaScript**, serving as an exact 1:1 implementation bridge between Figma source designs and engineering implementation.

---

## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Interactive Prototypes](#interactive-prototypes)
  - [1. Component Sandbox & Showcase](#1-component-sandbox--showcase-srcindexhtml)
  - [2. Enterprise Cloud FinOps Platform](#2-enterprise-cloud-finops-platform-srccloud-finopshtml)
- [Architecture & Tech Stack](#architecture--tech-stack)
  - [4-Layer Token System](#4-layer-token-system)
  - [Atomic Component Hierarchy](#atomic-component-hierarchy)
- [Project Directory Structure](#project-directory-structure)
- [Getting Started](#getting-started)
- [Design System & Engineering Standards](#design-system--engineering-standards)
- [Figma Source of Truth & Developer Handoff](#figma-source-of-truth--developer-handoff)
- [Contributing & Standards](#contributing--standards)

---

## Overview

This repository bridges product design and frontend engineering by implementing a complete, scalable design system inspired by **Figma shadcn/ui Pro Blocks** using modern web standards without framework overhead or heavyweight dependencies.

Every component, interaction, color variable, and state is mapped to tokenized variables, ensuring exact visual fidelity, dark/light theme switching, and strict accessibility standards.

---

## Key Features

- **Design Tokens First:** Over 850+ design tokens arranged in a 4-layer architecture using `oklch()` color spaces for dynamic palettes and contrast ratios.
- **Zero Framework Lock-in:** 100% pure semantic HTML5, modular CSS, and native JavaScript—drop-in ready for React, Vue, Svelte, or server-rendered architectures.
- **Figma Component Parity:** Structured directly from Figma file keys and design specifications, reproducing exact component variants, sizes, and states.
- **Accessibility (A11y) Compliant:** Built to meet **WCAG 2.2 AA** guidelines with native interactive elements (`<dialog>`, Popover API, `:focus-visible`, semantic ARIA attributes).
- **Dual Theme Support:** Real-time seamless light and dark mode switching via `[data-theme="light|dark"]`.
- **Premium Iconography & Typography:** Powered by [Geist](https://vercel.com/font) font and FontAwesome Pro 7.3.1 (`fa-light` style default).

---

## Interactive Prototypes

### 1. Component Sandbox & Showcase (`src/index.html`)
An interactive component explorer containing all 49+ design system primitives, molecules, organisms, and page blocks.
- **Live Variant Testing:** Buttons, Badges, Inputs, Sliders, Modals, Drawers, Sheets, and Tabs.
- **State Visualizers:** Default, Hover, Active, Focus, Disabled, Loading, Error, and Empty states.
- **Token Inspection:** Live dark/light theme switcher and variable token references.

### 2. Enterprise Cloud FinOps Platform (`src/cloud-finops.html`)
A complete, interactive SaaS enterprise application prototype simulating a modern cloud financial management dashboard.
- **Multi-Cloud Monitoring:** Track AWS, Azure, and GCP spending across accounts and regions.
- **Virtual Machines Cost Breakdown:** Azure VM inventory management with interactive sorting, multi-attribute filtering, and pagination.
- **Interactive KPI Cards:** Burn rates, budget forecasts, anomaly detections, and savings plans.
- **Interactive Charts & Visualizations:** Native SVG/CSS data visualization blocks.
- **Collapsible Application Shell:** Responsive sidebar navigation, user account switcher, and contextual breadcrumbs.

---

## Architecture & Tech Stack

### 4-Layer Token System

All styling is driven by cascading CSS Custom Properties defined in [`src/tokens/`](src/tokens/):

```
src/tokens/
├── primitives.css   # Layer 1: Raw values (Tailwind palettes, raw OKLCH/hex, base spacing, radii)
├── semantic.css     # Layer 2: Semantic roles (surface, border, text, foreground/background pairs)
├── theme.css        # Layer 3: Mode switching (:root, [data-theme="dark"], alpha overlays, charts)
├── typography.css   # Layer Typography: Font families, scale, line-heights, letter spacing
└── responsive.css   # Layer 4: Viewport-specific scales and container query tokens
```

### Atomic Component Hierarchy

Components follow Atomic Design principles located in [`src/components/`](src/components/):

| Layer | Component Categories | Examples |
| :--- | :--- | :--- |
| **Atoms** | Primitives & single-function elements | Button, Badge, Checkbox, Input, Kbd, Progress, Radio Group, Separator, Skeleton, Slider, Switch, Toggle, Tooltip |
| **Molecules** | Composite components with unified state | Accordion, Alert, Alert Dialog, Avatar, Breadcrumb, Button Group, Card, Collapsible, Combobox, Date Picker, Dialog, Drawer, Dropdown Menu, Empty State, Field, Hover Card, Input Group, Input OTP, Navigation Menu, Pagination, Popover, Select, Sheet, Toast / Sonner, Table, Tabs |
| **Organisms** | Complex, multi-feature UI sections | Activity Feed, App Header, Calendar, Chart Blocks, Data Grid, KPI Metrics, Sidebar Shell |
| **Blocks** | Ready-to-use page layouts and patterns | App Shell, Auth Forms, Dashboard Templates, Landing Blocks |

---

## Project Directory Structure

```text
design-prototypes/
├── .antigravity/            # AI agent instructions, rules, and design engineering standards
│   └── rules.md             # Design tokens and coding principles
├── docs/                    # Design handoff documentation & component registry
│   ├── FIGMA-COMPONENTS.md  # Full Figma token mappings, component matrix & states
│   └── SPECS-TEMPLATE.md    # Developer specification template for handoff
├── src/
│   ├── assets/              # Fonts, icons (FontAwesome Pro 7.3.1), and media assets
│   ├── components/          # Modular CSS component library
│   │   ├── atoms/           # Atomic CSS components
│   │   ├── molecules/       # Molecule CSS components
│   │   ├── organisms/       # Organism CSS components
│   │   ├── blocks/          # Page block layouts
│   │   └── components.css   # Single entry point importing all component layers
│   ├── tokens/              # 4-layer design token system
│   │   ├── tokens.css       # Unified entry point for tokens
│   │   ├── primitives.css
│   │   ├── semantic.css
│   │   ├── theme.css
│   │   ├── typography.css
│   │   └── responsive.css
│   ├── index.html           # Design System Sandbox & Component Showcase
│   └── cloud-finops.html    # Interactive Enterprise Cloud FinOps Application
└── README.md                # Project documentation
```

---

## Getting Started

Since the project uses zero build-step Vanilla HTML/CSS/JS, no compilation or bundler is required.

### 1. Clone the repository
```bash
git clone https://github.com/simoneborghimk-png/design-prototypes.git
cd design-prototypes
```

### 2. Run with a local static server

You can open the HTML files directly in any modern browser, or run a local HTTP server for optimal font and asset resolution:

Using **VS Code Live Server**:
- Right click on [`src/index.html`](src/index.html) or [`src/cloud-finops.html`](src/cloud-finops.html) and select **Open with Live Server**.

Using **Python 3**:
```bash
python3 -m http.server 3000
# Open http://localhost:3000/src/index.html or http://localhost:3000/src/cloud-finops.html
```

Using **Node.js (`npx serve`)**:
```bash
npx serve .
```

---

## Design System & Engineering Standards

1. **Token Usage Guarantee:** Never hardcode pixel values, hex colors, or custom transitions in component CSS. Always use tokens from `tokens.css`.
2. **Native Web APIs First:** Modals and Popovers utilize native HTML5 `<dialog>` and Popover API before falling back to JavaScript handlers.
3. **Accessibility (WCAG 2.2 AA):**
   - High-contrast color ratios preserved across both light and dark themes.
   - Distinct, visible `:focus-visible` outlines defined by token variables.
   - Keyboard navigation support (`Tab`, `Esc`, arrow keys) for dropdowns, drawers, and modal dialogs.
4. **BEM-Inspired & Modular CSS:** Strict modular class names avoiding style leaks or fragile descendant selectors.

---

## Figma Source of Truth & Developer Handoff

- **Figma File Key:** `pu2nlKYplmTCtTs0FVELdw` (`shadcn/ui kit for Figma + Pro Blocks - March 2026`)
- **Component Registry:** Refer to [`docs/FIGMA-COMPONENTS.md`](docs/FIGMA-COMPONENTS.md) for detailed property matrices, token mappings, and node references.
- **Handoff Specifications:** Use [`docs/SPECS-TEMPLATE.md`](docs/SPECS-TEMPLATE.md) when generating component implementation sheets for frontend development teams.

---

## License

This project is licensed under the MIT License - see the repository details for terms.
