# HaircutZonePro — Blogger Placement & Deployment Guide

This guide provides step-by-step instructions for placing your finalized **HaircutZonePro** affiliate content and website into your **Blogger (Blogspot)** site.

---

## 📁 What Files Are in Your Project

| File | Purpose | Where to Place in Blogger |
| :--- | :--- | :--- |
| **`blogger-article-post.html`** | In-depth affiliate article review with 4 top products, comparison matrix, pros & cons, and Amazon links. | **Blogger Dashboard → Posts → New Post** (HTML View) |
| **`blogger-theme.xml`** | Complete Blogger Theme XML template containing all 100 products, search engine, modal reader, FAQ, and responsive design. | **Blogger Dashboard → Theme → Edit HTML / Restore** |
| **`index.html`** | Standalone web page version (useful for static hosting, GitHub Pages, Netlify, or previewing locally). | Open in any browser or deploy to static web host |
| **`images/`** | 100 product images (`1.jpg`–`100.jpg`) + 6 article thumbnails (`article1.jpg`–`article6.jpg`). | Upload to Blogger Media, GitHub Pages, or free CDN |

---

## 🚀 PLACEMENT 1: Publishing the Long-Form Article in Blogger (5 Minutes)

Use this method to publish your high-converting review: *"Why Men Lose Hair: The Real Causes & The 2025 Clinically-Proven Regrowth Blueprint"*.

### Step-by-Step Instructions:

1. **Open Blogger Dashboard**:
   - Go to [blogger.com](https://www.blogger.com) and log into your account.
2. **Create New Post**:
   - In the left sidebar, click **Posts** → **+ NEW POST** (or orange button).
3. **Switch to HTML View**:
   - Look at the top-left toolbar of the post editor (next to the Undo/Redo arrows).
   - Click the pencil icon / **Compose view** dropdown and select **`<> HTML view`**.
4. **Copy & Paste the Code**:
   - Open [`blogger-article-post.html`](file:///l:/barber/blogger-article-post.html).
   - Copy **ALL** content inside `blogger-article-post.html`.
   - Paste it directly into the Blogger HTML editor (replace any existing text).
5. **Configure Post Settings** (Right sidebar in Blogger):
   - **Post Title**:
     ```text
     Why Men Lose Hair: The Real Causes & The 2025 Clinically-Proven Regrowth Blueprint
     ```
   - **Labels**:
     ```text
     Hair Growth, Scalp Care, Best Of, Product Reviews
     ```
   - **Search Description** (Under Post Settings → Search Description):
     ```text
     Discover the clinically proven causes of male hair thinning (DHT) and the top barber-tested products to halt hair loss and restore immediate density.
     ```
   - **Options**:
     - Reader comments: Allow (or Do not allow).
6. **Publish**:
   - Click **Preview** to verify the layout, then click **Publish** → **Confirm**!

---

## 🎨 PLACEMENT 2: Installing the Entire Website as your Blogger Theme (Full Portal)

Use [`blogger-theme.xml`](file:///l:/barber/blogger-theme.xml) if you want your whole Blogger blog to look like the luxury **HaircutZonePro** affiliate lab, including:
- Top 100 Product catalog with live search & instant category filters.
- Sticky header, mobile drawer menu, and reading progress bar.
- Interactive modal popups for 6 popular hair guides.
- Automatic rendering of your Blogger posts inside the dark luxury theme.

### Step-by-Step Instructions:

1. **Backup your current Blogger theme (Recommended)**:
   - Go to **Blogger Dashboard → Theme**.
   - Click the three dots icon (`⋮`) or dropdown next to **Customize** → click **Backup** → **Download**.
2. **Apply the New Theme**:
   - Method A (**Fastest via Restore**):
     1. Click the dropdown next to **Customize** → select **Restore**.
     2. Click **Upload**.
     3. Select the file [`l:\barber\blogger-theme.xml`](file:///l:/barber/blogger-theme.xml).
     4. Blogger will install and save the theme automatically!
   - Method B (**Via Edit HTML**):
     1. Click the dropdown next to **Customize** → select **Edit HTML**.
     2. Select all existing code (`Ctrl + A`) and delete it.
     3. Open [`l:\barber\blogger-theme.xml`](file:///l:/barber/blogger-theme.xml) in your code editor, copy everything (`Ctrl + A`, `Ctrl + C`), and paste it into Blogger's code window.
     4. Click the **Save** icon (diskette icon in the top-right corner).
3. **Turn Off Blogger Mobile Theme Default**:
   - On the **Theme** page, look for **Mobile Settings** (or the gear icon).
   - Ensure it is set to **Desktop** (or "No, show desktop theme on mobile devices"). Because `blogger-theme.xml` is already 100% mobile responsive with custom viewport handling.

---

## 🖼️ PLACEMENT 3: Handling Product Images on Blogger

On a local PC, images load from the local `images/` folder. When hosted on Blogger (`yourblog.blogspot.com`), you have 3 easy options for images:

### Option 1: Free Built-In SVG Placeholder (Zero Setup Needed)
The theme and post already include an automatic fallback engine. If any image file is not found, the site displays a sleek, branded dark-mode card with a barber pole icon and `HAIRCUTZONEPRO LAB` badge. No broken "X" icons will ever appear.

### Option 2: Host `images/` on GitHub Pages (Recommended — 2 Minutes)
1. Create a free GitHub repository (e.g. `haircut-assets`).
2. Upload the `images` folder from `l:\barber\images` into the repo.
3. Turn on **GitHub Pages** in Settings → Pages.
4. In `blogger-theme.xml` (or in Blogger Theme HTML editor), find line:
   ```javascript
   window.IMAGE_BASE_URL = '';
   ```
   and change it to your GitHub Pages URL:
   ```javascript
   window.IMAGE_BASE_URL = 'https://yourusername.github.io/haircut-assets/';
   ```
   All 100 images will instantly stream through GitHub's worldwide global CDN!

### Option 3: Blogger Native Image Uploader
1. In Blogger, create a new draft post titled *"Assets"* (keep it in Draft, don't publish).
2. Click the **Insert Image** button and upload your product photos from `l:\barber\images\`.
3. Blogger will assign each image a high-speed Google CDN URL (`https://blogger.googleusercontent.com/img/b/...`).
4. You can paste these Google URLs directly into your featured cards.

---

## 🏷️ PLACEMENT 4: Matching Blogger Labels & Navigation

The navigation bar in the theme links directly to standard Blogger label pages:
- `/search/label/Hair Growth`
- `/search/label/Scalp Care`
- `/search/label/Washing`
- `/search/label/Styling`
- `/search/label/Beard Care`
- `/search/label/Tools`
- `/search/label/Skincare`
- `/search/label/Lifestyle`
- `/search/label/Routines`
- `/search/label/Best Of`

When you write future posts in Blogger, simply type one or more of these labels in the **Labels** field on the right sidebar. The header menu and cards will automatically filter and display your posts!

---

## ⚖️ Legal & Compliance Pages in Blogger

The footer links to three standard Blogger static pages:
- `/p/privacy-policy.html`
- `/p/terms-disclaimer.html`
- `/p/affiliate-disclosure.html`

To create these:
1. In Blogger, click **Pages** in the left sidebar.
2. Click **+ NEW PAGE**.
3. Set the Title (e.g. *Affiliate Disclosure*), paste your legal text, and click **Publish**.
4. The footer links will automatically connect to them.
