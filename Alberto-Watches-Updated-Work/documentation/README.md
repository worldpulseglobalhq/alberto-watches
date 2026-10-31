# Alberto Watch Company — Aptech E-Project

A responsive, luxury-inspired watch-store project built with HTML5, CSS3, Bootstrap 5.3.8, jQuery 3.6.1, JavaScript, JSON, the Geolocation API and browser localStorage.

## Project structure
```
index.html          Home page (only file in the project root)
css/                style.css, responsive.css
js/                 config.js, main.js, products-data.js, vendor/jquery.min.js
images/             product images, clocks/, banners/ and the home-page videos (videos/)
pages/              every other HTML page (shop, cart, checkout, about, ...)
documentation/      README, project documents, diagrams, products.json
```
Pages inside `pages/` use `<base href="../">`, so every path is written from the project root (for example `images/logo.jpeg`, `pages/shop.html`).

## Run locally
1. Extract the ZIP.
2. Open a terminal in the project folder (the one that contains `index.html`).
3. Run `python -m http.server 8000`.
4. Visit `http://localhost:8000`.

The catalogue is loaded from `js/products-data.js`, so the site also opens by double-clicking `index.html`. Bootstrap and Google Fonts need an internet connection (jQuery is bundled locally).

## Main navigation
The top navigation stays simple: Home, Shop, About Us, Login / Sign Up and Cart. Additional Aptech project pages are available from the footer and Sitemap, including product details, categories, technology, gallery, store locator, contact, checkout, order confirmation, support, privacy, terms and shipping/returns.

## Catalogue and images
- There are 20 watch and 20 clock records in `js/products-data.js` (a copy is kept in `documentation/products.json`; keep both in sync when editing).
- Edit names, categories, prices, descriptions and features in `js/products-data.js`.
- Replace watch images at `images/1.jpeg` through `images/20.jpeg` and clock images in `images/clocks/`, keeping the same filenames.
- The logo is `images/logo.jpeg`.
- Product cards include **Add to Cart** and **Buy on WhatsApp**.
- Shop search, category filter, maximum-price filter and sorting are included.

## Change the coupon / discount
Open `js/config.js`. Change these settings:

```js
coupon: {
  code: "037123",   // change this, e.g. to "5570"
  percent: 20,      // change this, e.g. to 2 for 2% off
  active: true,
  minimumOrder: 0
}
```

The voucher card on Home and the checkout voucher field read the same configuration. Customers must enter the configured code at checkout and press **Apply**. The summary shows the discount and revised total. The code can be disabled by setting `active: false`.

## WhatsApp and checkout
- Set `whatsappNumber` in `js/config.js` to the verified business number in international digits-only format, e.g. `923XXXXXXXXX`.
- **Buy on WhatsApp** opens a premium checkout with a selected-watch preview and delivery form.
- Delivery fields include name, Pakistani mobile number, province dropdown (Punjab, Sindh, Khyber Pakhtunkhwa, Balochistan), city, area, full address, optional landmark and optional notes.
- The location button asks for permission only when clicked and attempts to fill a readable address. The customer should check and complete the address.
- Delivery charges are confirmed separately in WhatsApp; they are not silently added as a fixed website rule.
- The browser opens WhatsApp with a prefilled order message; the customer must review and press Send.

## Login / Sign Up limitation
The local demo allows a visitor to create an account and sign in on the same browser. A password hash is stored in browser localStorage, not a server database. This is suitable only for demonstrating a front-end flow and is **not production-grade authentication**. Do not reuse important passwords. A real store needs server-side authentication, HTTPS and secure account storage.

## Other limitations
- No online payment gateway, live inventory database, server-side order system, courier integration or real customer-message delivery is connected.
- Checkout opens WhatsApp; an order is not submitted until the customer sends the message.
- Product images, prices, testimonials and store details in the project are illustrative and should be verified before a real launch.
- Location detection depends on browser permission, HTTPS/localhost and the external address-lookup service.


## Latest visual and catalogue update
- Integrated the 20 supplied watch photographs into the numbered product images.
- Demo watch prices are in a PKR 3,199–3,999 range (clocks PKR 2,499–3,699) and refreshed short descriptions.
- The home page hero is a 3-video carousel (`images/videos/`), with banner images (`images/banners/`) as poster frames. Login page remains banner-free.
- Product prices and product details are demonstration content; verify real stock, brand, and specifications before publishing.

## Wishlist
- Hearts on product cards, the product details page and the Quick View popup; header heart icon (tablet/desktop) and a "Wishlist (n)" link in the mobile menu; page at `pages/wishlist.html`.
- Saved in this browser's `localStorage` under `albertoWishlist:user:<email>` (signed in) or `albertoWishlist:guest`. Guest items are merged into the account on login.
- Browser-only: there is no cross-device or cross-browser sync (that would need a backend).
- Code lives in the "Wishlist" block near the top of `js/main.js` and the "Wishlist" block at the end of `css/style.css`.
