# Geoffrey Woytt's Personal Portfolio Design System Specimen

(GitHub Repo)[https://github.com/Geoff12889/Design-System-Specimen]
(Published URL)[https://geoff12889.github.io/Design-System-Specimen/]

## Project

This project documents the foundation for a personal portfolio. It is intended for GIT337 assignment 1 / 📦 Deliverable: Design-System Specimen.

The page uses a personal portfolio style to demonstrate reusable CSS. It is a placeholder, not a complete portfolio.

## Sections

The single page includes the six required areas:

- S1: Foundations and reset
- S2: Token inventory
- S3: Typography
- S4: Actions and states
- S5: Surfaces and content patterns
- S6: Control foundations

The page also includes a portfolio introductions and about me section.

## Reset strategy

The stylesheet uses a compact reset:

- `box-sizing: border-box` is applied to all elements and their pseudo-elements so declared dimensions include padding and borders.
- Default margins are removed from the body, headings, and paragraphs so spacing can be set intentionally.
- Images and SVGs are block-level, constrained to their containers to prevent overflow.
- Buttons and inputs inherit the surrounding font styles while keeping native behavior.

Native form behavior is kept. A visible `:focus-visible` outline is added for keyboard navigation.

## Design tokens

Custom properties are grouped by category with descriptive prefixes:

- `--color-`
- `--font-`, `--size-` and `--line-height-`
- `--space-`
- `--content-width-` and `--control-height-`
- `--radius-`, `--border-width-` and `--shadow-`

The name of the tokens define their role. Components reference these tokens enabling website wide changes easily.

## Typography

The display font is Georgia, with Times new Roman and generic serif as backups. The UI uses Arial, with Helvetica and a generic sans-serif as backup.

The website does not download or include any fonts. It requests the font on the user's system. The styling uses regular, semi-bold, and bold font-weights. No italics are used.

The hero section sizes according to the clamp() function, scaling between a minimum and maximum font size. The heading and intro use a capped line width to keep them from spanning the entirety of the web page.

## Alternate theme

The `.theme-dark` class overrides color properties in the element containing this class. This keeps the dark theme palette to just the components contained in the element with the `.theme-dark` class.

## Accessibility and contrast

The page uses visible lables for controls and an outline with offset for keyboard focused elements.

The default color theme uses dark text on a light background with appropriate contrast ratio.

## Test record

The website is responsive at a wide 1280px, 768px, and a narrow 320px. The content reflows and there is no clipping or overflow unless the window gets down below 300px.

The website zooms appropriately and can be easily used at 2x.

Pressing tab on the keyboard navigates all the actionable elements on the page, with a visible outline to show which is the focus item.

The contrast is appropriate for both the light and dark themes.

The font falls back to the alternatives in the event the primary font is unavailable.

The HTML and CSS both validate using (Nu Html Checker)[https://validator.w3.org/nu/#textarea] and (The W3C CSS Validation Service)[https://jigsaw.w3.org/css-validator/#validate_by_input] respectively.

Loading the webpage in a private browser loads the same as a non-private browser.

## Code defense

The reset uses box sizing for predictable behavior when setting the dimensions of elements. The global tokens are organized into categories to help better navigate them. The dark theme class overrides the colors in the local scope it is used.

I made a revision to the responsive nature of the site after observing overlapping elements with the default `@media` query for 42rem. Because of this, I looked for how to use media queries to adjust content when a container shrink below a certain point, which brought me to the `@container` query. This solve the issue without needing to rework the entire section's HTML or CSS.