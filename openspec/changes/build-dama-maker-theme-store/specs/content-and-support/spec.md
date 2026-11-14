## ADDED Requirements

### Requirement: About page
The theme SHALL provide an about page template with configurable story, values, images, and call to action sections.

#### Scenario: Merchant edits the about page
- **WHEN** the merchant edits the about page sections in the theme editor
- **THEN** the published about page reflects the updated content and images

### Requirement: Contact page
The theme SHALL provide a contact page with a Shopify contact form and store contact details.

#### Scenario: Customer submits the contact form
- **WHEN** a customer submits a valid contact form
- **THEN** the form shows a success message and the submission is sent through Shopify

#### Scenario: Contact form validation
- **WHEN** a customer submits the contact form with missing required fields
- **THEN** accessible validation messages identify the fields that need attention

### Requirement: FAQ page
The theme SHALL provide an FAQ page with accessible accordion items.

#### Scenario: Customer expands an FAQ item
- **WHEN** a customer activates an FAQ question
- **THEN** the answer expands and the control exposes its expanded state to assistive technology

### Requirement: Blog
The theme SHALL provide a blog listing and article template with pagination, metadata, and shareable article content.

#### Scenario: Customer reads an article
- **WHEN** a customer opens a blog article
- **THEN** the page displays the title, publication date, author when available, content, and navigation back to the blog

#### Scenario: Blog listing pagination
- **WHEN** the blog has more articles than the configured page size
- **THEN** pagination controls allow the customer to reach older and newer articles

### Requirement: Policy pages
The theme SHALL render Shopify policy pages with readable typography and navigation.

#### Scenario: Policy page rendering
- **WHEN** a customer opens a privacy, refund, shipping, or terms policy page
- **THEN** the policy body renders in the theme layout with a clear page title

### Requirement: 404 page
The theme SHALL provide a 404 template with a clear message and links to continue shopping.

#### Scenario: Customer reaches a missing page
- **WHEN** a customer opens a URL that does not exist
- **THEN** the page displays a 404 message and links to the home page and main collections
