## ADDED Requirements

### Requirement: Product gallery
The product page SHALL display a gallery with a main image and selectable thumbnails for all product media.

#### Scenario: Customer selects a thumbnail
- **WHEN** a customer selects a thumbnail
- **THEN** the main image updates to the selected media and the selected thumbnail is visually indicated

#### Scenario: Keyboard gallery navigation
- **WHEN** a customer uses the keyboard to move between thumbnails
- **THEN** focus is visible and the main image updates without losing keyboard position

### Requirement: Variant selection
The product page SHALL provide variant selectors that update the selected variant, price, availability, and gallery when applicable.

#### Scenario: Customer selects an available variant
- **WHEN** a customer selects a variant combination that is available
- **THEN** the price, SKU when present, and availability reflect the selected variant

#### Scenario: Customer selects an unavailable variant
- **WHEN** a customer selects a variant combination that is unavailable
- **THEN** the add-to-cart action is disabled and an accessible message explains the unavailability

### Requirement: Add to cart
The product page SHALL allow customers to select a quantity and add the selected variant to the cart.

#### Scenario: Successful add to cart
- **WHEN** a customer adds an available variant to the cart
- **THEN** the cart count updates and an accessible confirmation is announced

#### Scenario: Add to cart error
- **WHEN** the add-to-cart request fails
- **THEN** the page displays an accessible error message and keeps the selected variant and quantity

### Requirement: Product information and trust
The product page SHALL display price, description, and configurable shipping, returns, or materials information.

#### Scenario: Merchant configures trust content
- **WHEN** the merchant edits shipping or returns information in the theme editor
- **THEN** the product page renders the updated information in an accessible layout

### Requirement: Related products
The product page SHALL render configurable related products from a selected collection.

#### Scenario: Related products are available
- **WHEN** the selected related collection contains products
- **THEN** the section renders product cards with links, images, titles, and prices

#### Scenario: Related products are empty
- **WHEN** the selected related collection has no products
- **THEN** the section hides without leaving an empty heading or layout gap

### Requirement: Product structured data
The product page SHALL output valid Product structured data including name, image, description, price, and availability.

#### Scenario: Search engine reads product data
- **WHEN** a search engine parses the product page
- **THEN** the page exposes Product structured data with the current variant price and availability
