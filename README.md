# FeniZ Online Shop

A PHP/MySQL ecommerce web application for product browsing, cart checkout, and admin management.

## Project Overview

FeniZ is a full-stack online store built with PHP, MySQL, HTML/CSS, and JavaScript. It includes separate user and admin experiences:

- Customer-facing storefront: product browsing, search, filter, cart, buy now, checkout, order history, contact page, profile access.
- Admin dashboard: charts, inventory and product management, reports, user and stock control.

## Tech Stack

- PHP 8+ (backend logic and page routing)
- MySQL / MariaDB (database)
- Bootstrap 5 (responsive UI)
- Font Awesome (icons)
- Chart.js (admin analytics charts)
- SweetAlert / Swal (notifications)
- PayHere JS SDK (checkout payment integration)
- JavaScript (frontend behavior, AJAX, cart actions)
- HTML/CSS (layout and styling)

## Core Files and Modules

- `index.php`: main product listing and search page
- `home.php`: landing page with hero banners and featured products
- `cart.php`: shopping cart page for logged-in users
- `checkoutProcess.php`: order checkout handler
- `buynowProcess.php`: immediate buy-now order handler
- `adminDashboard.php`: admin analytics and dashboard view
- `connection.php`: database helper class
- `FENIZ.sql`: database schema and initial data dump

Admin modules:

- `adminSignIn.php`, `adminSignInProcess.php`
- `adminProduct.php`, `adminStock.php`, `adminUser.php`
- `adminReport.php`, `adminReportProduct.php`, `adminReportStock.php`, `adminReportUser.php`
- `adminDelivery.php`, `adminNavBar.php`

Other key pages:

- `contact.php`: contact details and message form
- `forgetPassword.php`: password recovery
- `invoice.php`: order invoice generation
- `profile.php`: user profile and account actions
- `orderHistory.php`: user order history

## User Features

- Browse all products with live search
- Advanced filters by brand, category, color, type, and price range
- Add product to cart or buy immediately
- Checkout with cart contents and payment capture
- Order creation, order item tracking, order history
- User authentication and profile support
- Contact information page

## Admin Features

- Secure admin login
- Dashboard analytics: daily income, hourly income, best-selling products and categories
- Product, category, brand, color, and stock management
- User management and reporting
- Delivery and invoice controls

## Database

The app uses a MySQL database as defined in `FENIZ.sql`.

- Connection information lives in `connection.php`
- Default connection uses:
  - host: `127.0.0.1`
  - user: `root`
  - password: `Shehan@2002`
  - database: `feniz`
  - port: `3306`

Update these values before deployment or local testing.

## APIs and Backend Endpoints

This project does not expose a separate public REST API. Instead, PHP endpoints act as server-side handlers for the frontend:

- `checkoutProcess.php`: processes checkout orders and clears the cart
- `buynowProcess.php`: processes direct buy-now orders
- `adminSignInProcess.php`: handles admin authentication
- Multiple `*Process.php` files handle create/update/delete operations for brands, colors, categories, products, stock, and cart actions.

## Local Development Setup

1. Install a local PHP/MySQL stack such as XAMPP, WAMP, or MAMP.
2. Place the project folder inside your web server's document root.
3. Import `FENIZ.sql` into MySQL to create the database and tables.
4. Update database credentials in `connection.php` if needed.
5. Open the project in your browser via local URL, e.g. `http://localhost/feniz/`.

## Ngrok Usage

To expose your local app for testing or demo sharing, use ngrok:

1. Install ngrok from https://ngrok.com/
2. Run your local PHP server or use the web server URL.
3. Start ngrok on the port hosting your app, for example:

```bash
ngrok http 80
```

4. Use the public forwarding URL from ngrok to access your app remotely.

> If your local server listens on a different port, replace `80` with that port.

## Notes

- Ensure sessions are enabled in PHP and the server has write permissions if needed.
- The payment checkout flow uses the PayHere JS SDK, so a valid integration is required for real payments.
- Admin access is controlled by `user_type_id` in the users table.

## Recommended Improvements

- Add CSRF protection for form submissions
- Apply prepared statements to prevent SQL injection
- Build a dedicated REST API layer for external integrations
- Improve frontend accessibility and mobile UX
- Add detailed error handling for production

## Contact

For questions or updates, review `contact.php` and the project source directly.
