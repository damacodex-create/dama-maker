## ADDED Requirements

### Requirement: Cart surfaces
The theme SHALL provide a cart drawer from the header and a dedicated cart page.

#### Scenario: Customer opens the cart drawer
- **WHEN** a customer activates the cart button in the header
- **THEN** the drawer opens, moves focus into the drawer, and displays current line items and totals

#### Scenario: Customer opens the cart page
- **WHEN** a customer navigates to the cart page
- **THEN** the page displays the same line items, quantities, and totals as the drawer

### Requirement: Quantity and removal controls
Customers SHALL be able to update item quantities and remove line items from the cart.

#### Scenario: Customer updates quantity
- **WHEN** a customer changes the quantity of a line item
- **THEN** the line total and cart total update and the change is announced accessibly

#### Scenario: Customer removes an item
- **WHEN** a customer removes a line item
- **THEN** the item disappears from the cart and the updated total is announced accessibly

### Requirement: Cart totals
The cart SHALL display subtotal, discounts when present, shipping note, taxes note, and the final total available before checkout.

#### Scenario: Cart with discount
- **WHEN** the cart has an applied discount
- **THEN** the discount is displayed separately and the total reflects the discounted amount

### Requirement: Empty cart
The cart drawer and cart page SHALL display a clear empty state when no items are present.

#### Scenario: Empty cart page
- **WHEN** a customer opens the cart with no items
- **THEN** the page displays an empty-state message and a link to continue shopping

### Requirement: Checkout handoff
The cart SHALL provide a checkout action that sends the customer to Shopify checkout with the current cart.

#### Scenario: Customer proceeds to checkout
- **WHEN** a customer activates the checkout button with at least one item
- **THEN** the customer is taken to Shopify checkout with the current cart contents

#### Scenario: Checkout action while cart is empty
- **WHEN** the cart has no items
- **THEN** the checkout action is unavailable or clearly disabled

### Requirement: Cart accessibility
Cart interactions MUST be operable by keyboard and screen reader, and dynamic updates MUST be announced.

#### Scenario: Screen reader announces cart update
- **WHEN** a line item quantity changes
- **THEN** a polite live region announces the updated quantity and cart total
