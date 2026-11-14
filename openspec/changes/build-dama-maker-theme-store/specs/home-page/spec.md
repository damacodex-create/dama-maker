## ADDED Requirements

### Requirement: Hero section
The home page SHALL provide a hero section with configurable image, heading, subheading, call to action, and overlay treatment.

#### Scenario: Merchant edits hero content
- **WHEN** the merchant changes the hero heading, image, and CTA in the theme editor
- **THEN** the home page renders the updated content with the configured overlay and responsive image sizes

#### Scenario: Hero without image
- **WHEN** the merchant removes the hero image
- **THEN** the hero renders a usable text-only layout without empty space or broken image markup

### Requirement: Featured products
The home page SHALL render a configurable grid of products from a selected collection.

#### Scenario: Merchant selects a collection
- **WHEN** the merchant selects a collection and product limit for the featured products section
- **THEN** the section renders those products with image, title, price, and link to the product page

#### Scenario: Featured collection is empty
- **WHEN** the selected collection has no products
- **THEN** the section either hides or displays a clear empty-state message based on the configured setting

### Requirement: Category tiles
The home page SHALL render configurable collection tiles for product categories such as hogar, oficina, and accesorios.

#### Scenario: Merchant configures category tiles
- **WHEN** the merchant selects collections and labels for the category tiles section
- **THEN** each tile links to its collection and displays an accessible image and label

### Requirement: Brand story
The home page SHALL include a brand story section with configurable heading, text, image, and optional link.

#### Scenario: Brand story on mobile
- **WHEN** the brand story is viewed on a mobile viewport
- **THEN** image and text stack in a readable order without cropping essential content

### Requirement: Customer testimonials
The home page SHALL support configurable testimonial blocks with quote, author, and optional rating or avatar.

#### Scenario: Multiple testimonials
- **WHEN** the merchant adds three or more testimonial blocks
- **THEN** the section renders them in an accessible layout that remains readable on mobile

### Requirement: Newsletter signup
The home page SHALL provide a newsletter form that submits to Shopify's customer form and displays success and error feedback.

#### Scenario: Successful subscription
- **WHEN** a customer submits a valid email address
- **THEN** the form shows a success message and the page remains usable

#### Scenario: Invalid email
- **WHEN** a customer submits an invalid email address
- **THEN** the form shows an accessible error message and preserves the entered value

### Requirement: Home page presets
The home page SHALL be available as a theme editor preset with the required sections preconfigured.

#### Scenario: Merchant adds the home page preset
- **WHEN** the merchant adds the Dama Maker home preset in the theme editor
- **THEN** the page includes hero, featured products, categories, brand story, testimonials, and newsletter sections
