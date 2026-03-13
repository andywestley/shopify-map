# Shopify Product Map Section

A high-performance, responsive Shopify section that plots your products on an interactive map using Leaflet.js and OpenStreetMap.

![Shopify Map Demo](https://images.unsplash.com/photo-1526778548025-fa2f459cd5ce?auto=format&fit=crop&q=80&w=1000)

## Features
- **Interactive Map**: Built with Leaflet.js and OpenStreetMap (no API keys required).
- **Responsive Design**: Works perfectly on mobile, tablet, and desktop.
- **Advanced Filtering**: Filter products by collection directly from the map.
- **Location Search**: Users can search for locations via the Nominatim API.
- **"Near Me" Integration**: One-click geolocation to find products near the user.
- **Customizable Popups**: Shows product title, image, and price with a direct link to purchase.
- **Product Page Mode**: Includes a specialized section for individual product pages to show a local map.

---

## Deployment Instructions

### 1. Create the Metafield
You need a place to store the coordinates for your products.
1. Go to **Settings > Custom data > Products**.
2. Click **Add definition**.
3. Name: `Location`
4. Namespace and key: `custom.location`
5. Type: **Single line text**.
6. Ensure **"Storefronts"** access is checked and click **Save**.

### 2. Upload the Search API Template
This specialized template provides the data for the map.
1. In your Shopify Admin, go to **Online Store > Themes > Edit Code**.
2. Under **Templates**, click **Add a new template**.
3. Select **search** and name it `product-map-api`. (Filename: `search.product-map-api.liquid`).
4. Paste the code from `templates/search.product-map-api.liquid`.
5. Save.

### 3. Upload the Section
1. Under **Sections**, click **Add a new section**.
2. Name it `product-map`.
3. Paste the code from `sections/product-map.liquid`.
4. (Optional) Repeat for `sections/product-page-map.liquid` if you want a map on individual product pages.
5. Save.

### 4. Import Your Coordinates
The coordinates must be in the format `latitude,longitude` (e.g., `51.5074,-0.1278`).
- You can add these manually to each product in the **Metafields** section at the bottom of the product page.
- Or use the **Bulk Editor** to paste them in for multiple products at once.

---

## Technical Details
- **API Strategy**: Uses a custom Liquid search template to fetch JSON data, ensuring performance even with hundreds of pins.
- **Robust Metafield Loading**: Implements an `all_products` lookup trick to ensure metafields are reliably loaded across different themes.
- **Privacy**: No external tracking or required API keys.

## License
MIT
