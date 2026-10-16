# ARC/FORM — Premium Commerce Concept

A static, GitHub Pages-friendly storefront concept for FORM11 TECH STUDIOS. Built with semantic HTML, CSS and vanilla JavaScript. Product data is kept in `app.js` and mirrored in `assets/products.json` for convenient editing.

## Pages
- `index.html` — editorial homepage, featured products, campaign, departments, brand philosophy and product spotlight.
- `shop.html` — searchable collection, category filters, price range, sort modes and empty state.
- `product.html?id=orbit-watch` — reusable product template, options, quantity selector, specifications and related objects.
- `bag.html` — persistent bag with variant-aware items, quantity updates, removal and subtotal.
- `story.html` — brand story, principles, materials and demo shipping information.
- `404.html` — static-hosting not-found page.

## Run locally
Use a static server from the project directory. For example:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000/`. Do not open HTML files directly via `file://`, because local storage and relative resource behavior can differ.

## GitHub Pages
1. Create a repository named `arc-form-store` and upload the contents of this directory to its root.
2. In **Settings → Pages**, publish from the `main` branch and `/ (root)`.
3. The expected project URL format is `https://YOUR_USERNAME.github.io/arc-form-store/`.

The site uses relative internal links and has no build step. A static host serves it directly. Do not treat the expected URL as a live deployment until the repository is actually published.

## Verification
Run:

```bash
node --check app.js
node tests/qa.cjs
```

The QA script checks page files, product count, link targets, data wiring, reduced-motion support, and cart/search/filter behaviors by source-level assertions. A separate static server smoke test can confirm the files are served under `/arc-form-store/`.

## Notes and limitations
- This is a fictional portfolio storefront. No real payment, checkout, newsletter submission, inventory or order system is connected.
- Product and campaign photography uses remote Unsplash image URLs and Google Fonts. Those external requests require a network connection; the current build environment did not have outbound network access, so external asset delivery could not be verified here.
- The app has been checked with source-level tests and static hosting smoke tests. A full browser visual audit and end-to-end interaction test remain outstanding if no browser automation runtime is available.
- Contact and social links are clearly demo-oriented; the email uses the reserved `.example` domain.
