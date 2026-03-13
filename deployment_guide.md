# Shopify Theme Deployment Guide

Follow these steps to upload the map files to your Shopify theme and activate them.

## Step 1: Upload the Files
You need to copy the code from your workspace into your Shopify theme code editor.

1. In Shopify Admin, go to **Online Store** > **Themes**.
2. Click the **...** button next to your active theme and select **Edit code**.

### A. The Search API (Crucial for Data)
1. In the **Templates** folder, click **Add a new template**.
2. Select **search** and name it `product-map-api`.
3. Choose `.liquid` as the file type.
4. Replace the entire content with the code from: `templates/search.product-map-api.liquid`.

### B. The Main Map Section
1. In the **Sections** folder, click **Add a new section**.
2. Name it `product-map`.
3. Replace the entire content with the code from: `sections/product-map.liquid`.

### C. The Product Page Map Section
1. In the **Sections** folder, click **Add a new section**.
2. Name it `product-page-map`.
3. Replace the entire content with the code from: `sections/product-page-map.liquid`.

---

## Step 2: Add the Sections to Your Pages
Now that the code is uploaded, you can add them visually.

### To add the General Map:
1. Go to **Online Store** > **Themes** > **Customize**.
2. Navigate to the page where you want the map (e.g., a "Stockists" or "Locations" page).
3. In the sidebar, click **Add section**.
4. Search for **Product Map** and add it.
5. (Optional) Choose a specific collection to filter the pins in the section settings.

### To add the Individual Product Map:
1. In the Theme Customizer, use the top dropdown to navigate to **Products** > **Default product**.
2. In the sidebar, click **Add section**.
3. Search for **Product Page Map**.
4. This map will *only* appear if that specific product has coordinates in its `custom.location` metafield.

---

## How it works (The Technical Bit)
- The **Product Map** section automatically "asks" the **Search API** for a list of products that have locations.
- It uses the URL `/search?view=product-map-api` to get that data in a clean JSON format.
- If you change a product's location in the Shopify admin, it will update on the map automatically (though it might take a minute for Shopify's cache to refresh).
