## ADDED Requirements

### Requirement: Product grid
Collection pages SHALL render products in a responsive grid with image, title, price, and availability.

#### Scenario: Collection with products
- **WHEN** a customer opens a collection with products
- **THEN** the page renders product cards in a responsive grid without layout overflow

#### Scenario: Product card without image
- **WHEN** a product has no featured image
- **THEN** the card renders a placeholder that preserves the grid layout and accessible product name

### Requirement: Pagination
Collection pages SHALL paginate results when the product count exceeds the configured page size.

#### Scenario: Customer moves to the next page
- **WHEN** a customer activates the next-page control
- **THEN** the next set of products loads and the current page is indicated accessibly

### Requirement: Filtering and sorting
Collection pages SHALL expose available filters and sorting controls that update the result set.

#### Scenario: Customer applies a filter
- **WHEN** a customer selects a filter value
- **THEN** the product grid updates to match the filter and the active filter is visible and removable

#### Scenario: Customer changes sort order
- **WHEN** a customer selects a different sort order
- **THEN** the product grid updates to the selected order and the URL reflects the selection

### Requirement: Search results
The theme SHALL provide a search results page that reuses the product card grid and displays the query.

#### Scenario: Search with results
- **WHEN** a customer searches for a term that matches products
- **THEN** the page displays the query and matching products with links to each product

#### Scenario: Search without results
- **WHEN** a customer searches for a term with no matches
- **THEN** the page displays a clear empty state with suggestions and a way to continue browsing

### Requirement: Collection SEO and navigation
Collection pages SHALL output a collection-specific title, description when available, canonical URL, and breadcrumb navigation.

#### Scenario: Collection metadata
- **WHEN** a collection page is rendered
- **THEN** the page includes the collection title, description, canonical URL, and breadcrumb links
