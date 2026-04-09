# Design System Specification: Tactical Precision

## 1. Overview & Creative North Star: "The Command Console"
This design system rejects the "friendly" softness of modern SaaS in favor of **Tactical Precision**. Our Creative North Star is the high-end digital cockpit—a mission-critical environment where information density, authority, and utility are paramount. 

We break the standard "web template" aesthetic by utilizing a rigid, 0px border-radius architecture and high-contrast tonal layering. The experience should feel like a physical operations dashboard: sturdy, purposeful, and immovable. By removing "lifestyle" fluff and rounded edges, we create a signature visual identity that honors the disciplined nature of military life.

## 2. Color Strategy & Tonal Architecture
The palette is rooted in deep authority and grounded tactical utility. We do not use color for decoration; we use it for status and hierarchy.

### The "No-Line" Rule
**Explicit Instruction:** Traditional 1px solid borders for sectioning are strictly prohibited. Boundaries must be defined solely through background color shifts or subtle tonal transitions.
- Use `surface` (#f9f9ff) for the base canvas.
- Use `surface-container-low` (#f0f3ff) or `surface-container` (#e7eefe) to define distinct content zones.
- This creates a seamless, "milled" look where components appear to be part of the same physical structure.

### Surface Hierarchy & Nesting
Hierarchy is achieved through "Tonal Stacking."
1. **Primary Navigation/Sidebar:** `primary-container` (#1e3a5f) to establish a heavy, authoritative anchor.
2. **Main Workspace:** `surface` (#f9f9ff).
3. **Information Modules:** `surface-container-lowest` (#ffffff) to "pop" critical data without using shadows.
4. **Active/Tactical Overlays:** Use `secondary-container` (#fecf4f) sparingly for mission-critical alerts or active states.

### Signature Textures & Glassmorphism
To avoid a "flat" corporate feel, utilize **HUD-style Glassmorphism** for floating elements (modals, tooltips). Use `surface-variant` with 80% opacity and a 12px backdrop-blur to mimic a Head-Up Display (HUD) overlay. Apply subtle linear gradients from `primary` (#022448) to `primary-container` (#1e3a5f) on large interactive surfaces to provide a metallic, satin finish.

## 3. Typography: The Editorial Blueprint
Our typography pairs the industrial strength of **Barlow** with the technical clarity of **Inter**.

- **Headlines (Barlow, 700):** Used for `display` and `headline` tiers. The slightly condensed nature of Barlow evokes military stencil and technical manuals. It should feel loud, authoritative, and unapologetic.
- **Body & Labels (Inter, 400/500):** Used for `title`, `body`, and `label` tiers. Inter provides the modern, professional legibility required for high-density data. 
- **The Identity Gap:** Use high-contrast sizing. A `display-lg` headline should often sit adjacent to a `label-sm` technical metadata string to create an "Editorial Dashboard" look.

## 4. Elevation & Depth: Tonal Layering
In this design system, "Up" does not mean "Shadow." It means "Contrast."

- **The Layering Principle:** Depth is achieved by stacking `surface-container` tiers. Place a `surface-container-lowest` card on a `surface-container-low` background. The subtle shift in hex value provides a sophisticated, natural lift.
- **Ambient Shadows:** Shadows are reserved for floating mission-critical elements only. They must be extra-diffused (Blur: 24px+) and extremely low opacity (4%-6%), using a tint of `on-surface` (#151c27) rather than pure black.
- **The "Ghost Border" Fallback:** If accessibility requires a container definition, use the `outline-variant` token at 15% opacity. Never use 100% opaque lines.
- **Hard Edges:** Every component—buttons, cards, inputs—must maintain a **0px border-radius**. This is the core signature of the system’s "Tactical" feel.

## 5. Components

### Buttons: Tactical Actuators
- **Primary:** `primary` (#022448) background with `on-primary` (#ffffff) text. 0px radius. Bold, uppercase Barlow.
- **Secondary (The Brass Insignia):** `secondary` (#765b00) background. Used for the "Mission Critical" path.
- **Tertiary:** `outline` text with no background. Interaction state is defined by a subtle `surface-container-highest` background shift on hover.

### Inputs: Technical Fields
- **Styling:** Use `surface-container-high` backgrounds with a bottom-only "Ghost Border" (2px) of `primary`. 
- **States:** On focus, the bottom border transitions to `secondary` (Military Gold). 
- **Density:** Keep padding tight (8px-12px) to maintain high information density.

### Cards & Lists: Data Containers
- **Prohibition:** No divider lines.
- **Separation:** Use 24px or 32px of vertical whitespace or a subtle background toggle between `surface` and `surface-container-low`.
- **Header:** Every card should lead with a `label-md` in `on-tertiary-container` to act as a "Technical Category Tag."

### Additional Component: The "Mission HUD" Status Bar
A custom component for housing platforms. A thin, horizontal bar using `tertiary-container` that displays mission metadata (PCS Date, Location, Order Status) in `label-sm` Inter, separated by `secondary` (Military Gold) chevrons.

## 6. Do’s and Don’ts

### Do:
- **Embrace Density:** It is okay for the UI to look "complex" as long as it is organized. Think of a pilot's cockpit.
- **Use Monospace Accents:** For numerical data or coordinates, use a monospace font-variant to enhance the tactical feel.
- **Utilize Tactical Icons:** Use thin-stroke icons inspired by compasses, chevrons, and rank insignias.

### Don’t:
- **No Rounded Corners:** Never use a border-radius. 0px is the law.
- **No Lifestyle Imagery:** Avoid "happy family moving into a house" photos. Use architectural photography, maps, and technical schematics.
- **No Center Alignment:** Use strong left-aligned grids to maintain an authoritative, document-like flow.
- **No "Soft" Colors:** Avoid pastels. If a color isn't in the palette, it doesn't exist in the mission.