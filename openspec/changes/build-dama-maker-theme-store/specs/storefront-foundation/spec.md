## ADDED Requirements

### Requirement: Global brand settings
The theme SHALL expose global settings for logo, color palette, typography, spacing, and social links in the theme editor.

#### Scenario: Merchant updates brand color
- **WHEN** the merchant changes the primary brand color in theme settings
- **THEN** components using the primary color render with the new value without code changes

#### Scenario: Merchant uploads a logo
- **WHEN** the merchant uploads a logo image
- **THEN** the header renders the logo with accessible alternative text and responsive dimensions

### Requirement: Responsive layout
The storefront MUST render without horizontal overflow from 320 px to 1440 px viewport widths.

#### Scenario: Mobile viewport
- **WHEN** the storefront is viewed at 320 px width
- **THEN** navigation, product grids, forms, and cart remain usable and no horizontal scrolling is introduced

#### Scenario: Desktop viewport
- **WHEN** the storefront is viewed at 1440 px width
- **THEN** content uses the intended grid and max-width without stretching beyond the content container

### Requirement: Header and footer navigation
The theme SHALL provide a header with logo, primary navigation, search access, and cart access, and a footer with menu, contact, and policy links.

#### Scenario: Mobile navigation
- **WHEN** a customer opens the mobile menu
- **THEN** the menu is keyboard operable, moves focus into the menu, and closes with Escape

#### Scenario: Cart access
- **WHEN** a customer activates the cart link or button
- **THEN** the cart drawer or cart page opens with the current item count announced

### Requirement: SEO and social metadata
Every template SHALL output a unique page title, meta description when available, canonical URL, and Open Graph metadata.

#### Scenario: Product page metadata
- **WHEN** a product page is rendered
- **THEN** the page includes the product title, description, canonical URL, and Open Graph product metadata

### Requirement: Accessibility foundation
The theme MUST provide a skip link, visible focus styles, semantic landmarks, and reduced-motion support.

#### Scenario: Keyboard-only navigation
- **WHEN** a customer navigates the storefront using only the keyboard
- **THEN** the skip link is the first focusable element, focus is always visible, and main content is reachable

#### Scenario: Reduced motion
- **WHEN** the customer has `prefers-reduced-motion: reduce` enabled
- **THEN** non-essential animations are disabled or reduced

### Requirement: Theme editor organization
Theme settings and section schemas SHALL use clear groups, labels, and informative defaults.

#### Scenario: Merchant finds a setting
- **WHEN** the merchant opens the theme editor
- **THEN** settings are grouped by purpose and each label describes the resulting visual change
