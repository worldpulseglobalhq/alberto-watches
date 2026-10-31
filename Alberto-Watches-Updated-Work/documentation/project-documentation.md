# Alberto Watch Company — Project Documentation

## 1. Introduction
This Aptech eProject store demonstrates a responsive luxury-inspired watch catalogue and front-end shopping flow. It uses HTML5, CSS3, Bootstrap 5, jQuery, JavaScript, JSON and browser localStorage.

## 2. Objectives
- Present a responsive multi-page watch store with consistent branding.
- Display 40 product records (20 watches and 20 clocks) with numbered image assets.
- Provide search, category filtering, maximum-price filtering and sorting.
- Provide product detail views, persistent cart quantities and removal.
- Add a configurable coupon that recalculates the checkout total.
- Provide a premium two-column checkout with watch preview and delivery details.
- Prepare a WhatsApp order message after form validation.
- Demonstrate sign-up and login flow on the same browser.
- Include gallery, support, policy and educational pages required for the eProject.

## 3. Technologies
- HTML5 and CSS3
- Bootstrap 5.3.8 CDN
- jQuery 3.6.1 (local copy in `js/vendor/jquery.min.js`)
- JavaScript and JSON
- Browser localStorage
- HTML5 Geolocation API and OpenStreetMap Nominatim reverse geocoding

## 4. Project structure
- `index.html` (home) in the root and the other pages in `pages/`: shop, product, categories, technology, gallery, locator, about, contact, login, signup, cart, checkout, confirmation, support, sitemap and legal pages.
- `css/style.css`: shared design system and responsive premium styles.
- `css/responsive.css`: responsive layout rules.
- `js/main.js`: page rendering (all pages are rendered by this one script), catalogue interaction, cart, coupon application, checkout, login/signup and location helper.
- `js/config.js`: WhatsApp number and editable coupon settings.
- `documentation/products.json`: 40 product records (20 watches and 20 clocks); `js/products-data.js` holds the same data for direct loading.
- `images/1.jpeg` through `20.jpeg`: numbered watch images; `images/clocks/`: clock images; `images/banners/` and `images/videos/`: home-page hero; `logo.jpeg`: logo.
- `documentation/`: project notes, test cases and flow diagrams.

## 5. Coupon logic
`pages/discount.html` displays the active offers. The coupon is configured in `js/config.js` with `code`, `percent`, `active` and `minimumOrder`. The customer enters the configured code on checkout and presses Apply. Invalid/inactive codes are rejected. The checkout summary displays subtotal, coupon saving and total before delivery.

## 6. Cart and WhatsApp ordering
The cart is stored in localStorage and can be updated or cleared. A product's Buy on WhatsApp button opens checkout for that product; checkout from the cart uses all cart items. The delivery form validates the required fields and Pakistani mobile number before preparing a WhatsApp message. Delivery charges are confirmed separately. The customer must press Send in WhatsApp to actually submit the order.

## 7. Login / Sign Up
Sign-up checks required fields, password confirmation and Pakistani phone format. A SHA-256 password hash and random salt are saved in browser localStorage for this educational store, allowing a matching local login. This is not a secure authentication architecture and must not be used for real customer accounts; a production site requires server-side authentication.

## 8. Testing status
Automated checks verify JavaScript syntax, JSON validity, page references, numbered image mapping and presence/order of Bootstrap, jQuery, configuration and application scripts. Full interactive browser testing should be completed in a browser before submission or deployment.

## 9. Limitations
The project has no production backend, secure customer database, payment gateway, courier integration, verified inventory or server-side coupon validation. Browser-side coupon values can be changed by a visitor and are intended for an academic store. All illustrative product claims, prices, images, testimonials and business details should be verified before public launch.
