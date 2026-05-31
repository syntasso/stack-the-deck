# White-Label Adaptation Guide

This guide explains how to adapt *Stack the Deck* for your own platform engineering workshops under the terms of [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). It covers what must be preserved, what may be freely replaced, how to attribute the original work, and practical guidance for editing each file type.

---

## Table of Contents

1. [What to Preserve](#1-what-to-preserve)
2. [What to Replace Freely](#2-what-to-replace-freely)
3. [Attribution Requirements](#3-attribution-requirements)
4. [File-by-File Editing Guide](#4-file-by-file-editing-guide)
5. [Recommended Repository Structure for Derivatives](#5-recommended-repository-structure-for-derivatives)
6. [Community Adaptations](#6-community-adaptations)

---

## 1. What to Preserve

The following elements constitute the **core intellectual contribution** of this game. They should be maintained in any derivative to ensure the game retains its educational value and internal consistency.

### The Four Principles of an Effective Platform

These principles form the conceptual foundation of the game and underpin the card design. They must not be removed or substantially altered.

| # | Principle |
|---|-----------|
| 1 | Self-service and on-demand access |
| 2 | Incorporated business processes |
| 3 | Fleet-managed services at scale |
| 4 | Direct contribution from domain experts |

### The Six Card Categories

These categories define the game's API design methodology. The category names and their functional definitions must be preserved.

| Category | Definition |
|---|---|
| **Inputs** | What users can or should configure |
| **Outputs** | What users depend on to access and maintain their resources |
| **Provisioning Actions** (shared) | Actions that occur for all resources before any request |
| **Process Rules** (shared) | Rules applied to all resources before any request |
| **Provisioning Actions** (per-request) | Actions that occur per individual request |
| **Process Rules** (per-request) | Rules applied per individual request |
| **Interfaces** | How users interact with the platform service |
| **Destinations** | Where provisioned resources are deployed or delivered |

### The Board Layout Structure

The three-tier board structure (API tier, Service tier, Platform tier) defines the game's reasoning model. The spatial relationships between zones must be maintained.

---

## 2. What to Replace Freely

The following elements are **brand and product-specific** and are intended to be replaced in derivative works. CC BY 4.0 does not grant trademark rights; replacing these elements is both permitted and appropriate.

| Element | Location | Replacement guidance |
|---|---|---|
| Company name ("Syntasso") | `README.md`, SVG files, card PDF | Replace with your organization name, or use a generic/neutral label |
| Product name ("Kratix", "Syntasso Kratix Enterprise") | `README.md`, card PDF | Replace with your tooling name, or use neutral language such as "platform orchestration tooling" |
| Company logo | `board_mat-size61x36.svg`, `pack.svg` | Replace with your logo, or remove entirely |
| Color scheme | `board_mat-size61x36.svg`, `pack.svg`, `cards.pdf` | Freely adapt to match your organization's brand guidelines |
| Miro template link | `README.md` | Replace with your own Miro/FigJam/Mural template, or remove the section |
| Example service names on cards | `cards.pdf` | Replace with examples relevant to your audience's domain or technology stack |
| Printer recommendations | `README.md` | Add or substitute printers available in your region |

---

## 3. Attribution Requirements

CC BY 4.0 requires that you credit the original work in any derivative. Attribution must be **reasonably prominent** and included in all distributed forms (digital and physical).

### Minimum required attribution

```
Adapted from "Stack the Deck" by Syntasso
https://github.com/syntasso/stack-the-deck
Licensed under CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/)
Modifications: [brief description of your changes]
```

### Recommended placement

| Format | Placement |
|---|---|
| GitHub repository | `README.md` Credits section, and/or `CREDITS.md` |
| Printed card deck | Back of the pack card or inside the box |
| Printed board mat | Footer or reverse side of the board |
| PDF cards | Footer of the first or last card |
| Virtual board (Miro/FigJam) | Board description field or a dedicated sticky note frame |
| Workshop slide deck | Final "References" slide |


### What attribution does NOT require

- Retaining the Syntasso logo in the visual assets
- Retaining the Kratix product name on cards
- Using the same title ("Stack the Deck") for your derivative (though you may)
- Syntasso's endorsement or approval of your adaptation

---

## 4. File-by-File Editing Guide

### `README.md`

Plain text/Markdown. Edit freely in any text editor.

- Replace all occurrences of "Syntasso" and "Kratix" with your organization and tooling names, or with neutral equivalents
- Update the Miro template link to point to your own virtual board
- Add an attribution section (see Section 3)
- Update the `CHANGES.md` entry describing your modifications

### `board_mat-size61x36.svg/jpg`

SVG is an XML-based text format and can be edited with:
- **Inkscape** (free): open directly, edit text nodes and replace logo elements
- **Figma** (browser-based): import SVG, edit, export
- **Any text editor**: search for brand name strings and replace; locate `<image>` or `<path>` nodes for logo removal

Key items to locate and edit:
- Text nodes containing "Syntasso" or "Kratix"
- `<image>` elements embedding the company logo
- Color values in `fill` and `stroke` attributes if rebranding

After editing, re-export as SVG and regenerate the JPG (`board_mat-size61x36.jpg`) at 150–300 DPI for print.

### `pack.svg/jpg`

Same approach as the board mat SVG above. The pack face typically contains the company name and logo. Replace or remove these elements and update the color scheme to match your branding.

### `cards.pdf`

PDF is a binary-adjacent format and is the most challenging file to edit without the original source. Recommended approaches:

1. **If source files are available** : edit in the original tool and re-export to PDF. Request source file access from the maintainers if not publicly provided.

2. **If only the PDF is available**: use a PDF editor to overwrite text layers. Note that embedded fonts may affect fidelity.

3. **Recreate from scratch**: for full control and the cleanest result, recreate the card layout using your own design tooling, using the original as a visual reference. This is recommended for language localization (e.g., Japanese), as right-to-left text flow and CJK fonts require layout-level changes.

Document any recreation or substantial modification in your `CHANGES.md`.

### `alternate board formats/`

These contain alternative print layouts (A4, A2). Apply the same edits as the main board mat, adapted for each page size. Verify print margins after editing.

---

## 5. Recommended Repository Structure for Derivatives

```
your-repo/
├── LICENSE                  # CC BY 4.0 license text
├── CREDITS.md               # Attribution to the original work
├── CHANGES.md               # Record of modifications made
├── README.md                # Your adapted documentation
├── WHITE-LABEL.md           # This file (optional: retain for your own adapters)
│
├── board_mat-size61x36.svg  # Adapted board mat (SVG)
├── board_mat-size61x36.jpg  # Adapted board mat (JPG for print)
├── pack.svg                 # Adapted card pack face (SVG)
├── pack.jpg                 # Adapted card pack face (JPG)
├── cards.pdf                # Adapted card deck (PDF)
│
└── alternate board formats/
    └── ...                  # Adapted alternate format files
```

### `CREDITS.md` template

```markdown
# Credits

This project is adapted from **Stack the Deck** by Syntasso.

- Original repository: https://github.com/syntasso/stack-the-deck
- Original license: Apache 2.0 (original) / CC BY 4.0 (as of May 27th,2026)
- This adaptation is licensed under: CC BY 4.0

## Modifications

- [List your changes here, e.g.:]
- Translated all card text and board labels into Japanese
- Replaced Kratix-specific card examples with vendor-neutral equivalents
- Updated color scheme and removed Syntasso logo
- Adapted example services for [your domain] context
```

### `CHANGES.md` template

```markdown
# Change Log

## [Your version or date]

### Modified files
- `README.md`: Replaced Syntasso/Kratix references; added attribution section
- `board_mat-size61x36.svg`: Removed Syntasso logo; replaced company name; updated colors
- `pack.svg`: Replaced pack face branding
- `cards.pdf`: [Describe edits or note "recreated from scratch"]

### Preserved elements
- Four platform principles (unchanged)
- Six card categories and definitions (unchanged)
- Three-tier board layout structure (unchanged)
```

---

## 6. Community Adaptations

If you create a derivative adaptation, consider contributing it back to the `examples/` directory of this repository (if established) or linking to it from the original repository's Discussions section. This helps other practitioners discover localized or domain-specific versions of the game.

When sharing a derivative publicly:

- Ensure your repository includes `LICENSE` (CC BY 4.0) and `CHANGES.md`
- Mention the adaptation in your repository description (e.g., "Japanese-language adaptation of Stack the Deck")
- Optionally include the attribution badge in your `README.md`

---

*This WHITE-LABEL.md was contributed by the community and is itself licensed under CC BY 4.0.*
