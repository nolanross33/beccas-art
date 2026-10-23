# Becca's Customs — Portfolio Site

Static HTML/CSS/JS portfolio for custom pet portraits and architectural illustrations. Deploys directly via GitHub Pages with no build step.

## Folder structure

```
beccas-art/
├── index.html        ← single-page site
├── styles.css
├── script.js
├── CNAME             ← custom domain (beccascustoms.com)
├── README.md
└── images/
    ├── portrait-1.jpg      ← golden retriever
    ├── portrait-2.jpg      ← tabby cat
    ├── portrait-3.jpg      ← French bulldog
    ├── portrait-4.jpg      ← chestnut horse
    ├── arch-1.jpg          ← Brooklyn brownstone
    ├── arch-2.jpg          ← country farmhouse
    ├── arch-3.jpg          ← Victorian cottage
    ├── arch-4.jpg          ← mountain cabin
    └── about-becca.jpg     ← photo of Becca for the About section
```

---

## Adding new gallery images

1. **Drop the image file** into the `images/` folder. Use a descriptive filename (e.g., `portrait-labrador.jpg`). JPEG or WebP at ~1200px on the longest edge works well for both preview and lightbox quality.

2. **Add a new `<article>` block** inside the `<div class="gallery-grid">` in `index.html`. Copy an existing item and update three things:

   ```html
   <article class="gallery-item" data-category="portrait" tabindex="0" role="button"
            aria-label="View: [Short description of the piece]">
     <div class="gallery-thumb">
       <img src="images/your-filename.jpg"
            alt="[Descriptive alt text for accessibility]"
            loading="lazy">
       <div class="gallery-overlay" aria-hidden="true">
         <!-- keep the SVG icon as-is -->
       </div>
     </div>
   </article>
   ```

   - Set `data-category` to `portrait` or `architecture` so the filter buttons work.
   - Write a meaningful `alt` attribute (screen readers and SEO both use it).

3. **Save and push** — that's it. No build step needed.

---

## One-time setup checklist

### Email address
In `index.html`, replace both instances of `YOUR_EMAIL_HERE` (in the commission form note and the footer nav) with Becca's real email address.

### Formspree (commission form)
1. Create a free account at [formspree.io](https://formspree.io).
2. Create a new form and copy the form ID (looks like `xabcdefg`).
3. In `index.html`, find the `<form>` tag and replace `YOUR_FORMSPREE_ID`:
   ```html
   action="https://formspree.io/f/xabcdefg"
   ```
4. Verify the form by submitting a test inquiry — Formspree will send a confirmation email.

### About section placeholder text
The About section contains placeholder copy marked with `[City, State]` — update that with Becca's real location and edit the bio text to match.

---

## Deploying to GitHub Pages

1. Create a new **public** GitHub repository (e.g., `beccas-art`).
2. Push this folder to the `main` branch.
3. Go to **Settings → Pages**, set Source to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. GitHub will publish the site at `https://<your-username>.github.io/beccas-art`.

### Custom domain (beccascustoms.com)
The `CNAME` file is already in place. In your domain registrar's DNS settings, add:

| Type  | Host | Value                          |
|-------|------|--------------------------------|
| A     | @    | 185.199.108.153                |
| A     | @    | 185.199.109.153                |
| A     | @    | 185.199.110.153                |
| A     | @    | 185.199.111.153                |
| CNAME | www  | `<your-username>.github.io`    |

DNS changes can take up to 48 hours. Once propagated, enable **Enforce HTTPS** in the GitHub Pages settings.
