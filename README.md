# Tara-Sakhi Website — How to Add New Products Daily

You never need to edit the website's design code again. Adding a new product
is just two steps: **upload a photo** and **add one entry to a text file**.

## Folder structure

```
tara-sakhi/
├── index.html          ← the website (never edit this for new products)
├── products.json        ← the list of products (edit THIS to add items)
└── images/
    ├── frocks/
    ├── lehengas/
    ├── croptops/
    ├── kurtis/
    └── blouses/
```

## Adding a new product (daily workflow)

**Step 1 — Add the photo**
Upload your product photo into the matching folder inside `images/`.
Example: a new frock photo goes in `images/frocks/`.
Name it something simple with no spaces, e.g. `frock-05.jpg`.

**Step 2 — Add one entry to `products.json`**
Open `products.json` (on GitHub: click the file, then the pencil ✏️ icon
to edit it in your browser). Copy one existing entry and change the details:

```json
{ "id": "frock-05", "category": "frocks", "name": "Silk Cotton Frock", "price": "₹2,650", "fabric": "Silk Cotton", "badge": "New", "image": "images/frocks/frock-05.jpg" },
```

- `category` must be one of: `frocks`, `lehengas`, `croptops`, `kurtis`, `blouses`
- `image` must match the exact filename you uploaded in Step 1
- `badge` is optional — leave it as `""` if you don't want a tag like "New"
- Don't forget the comma at the end of the line (except for the very last entry in the file)

**Step 3 — Save / commit**
On GitHub, scroll down and click **"Commit changes"**. Within about a minute,
the new product appears live on the site in its category section — no other
code needs to change.

## If a photo is missing

If `products.json` references an image that hasn't been uploaded yet, the
website won't break — that product tile will show a soft placeholder with
the exact filename it's expecting (e.g. "Add photo: images/frocks/frock-06.jpg"),
so you always know exactly what to upload next.

## Removing a product

Delete its `{ ... }` entry from `products.json` and commit. You can leave the
photo in the `images/` folder — it just won't show anywhere until it's
referenced again.

## Adding a whole new category

1. Add a folder under `images/`, e.g. `images/sarees/`
2. Add products to `products.json` with `"category": "sarees"`
3. In `index.html`, find the `CATEGORY_META` list near the bottom of the
   `<script>` section and add one line:
   `{ key: 'sarees', title: 'Sarees' },`
   (This is the one time you'd touch `index.html` — only when introducing a
   brand-new category, not for everyday new products.)
