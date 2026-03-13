# Shopify Metafield Setup & Import Guide

Follow these steps to add the geocoded locations to your Shopify products.

## Step 1: Create the Metafield Definition
Before you can store the coordinates, you must define the field in your Shopify settings.

1. In your Shopify Admin, go to **Settings** > **Custom data**.
2. Click on **Products**.
3. Click **Add definition**.
4. Set the following values:
   - **Name**: `Location`
   - **Namespace and key**: `custom.location` (This must match the code exactly)
   - **Type**: Select **Single line text**.
5. Click **Save**.

## Step 2: Open the Bulk Editor
Shopify has a hidden "Bulk Editor" that makes it easy to paste values.

1. Log in to your Shopify Admin.
2. In your browser's address bar, paste the following URL (replace `[your-store-name]` with your actual store handle):
   `https://admin.shopify.com/store/[your-store-name]/bulk?resource_name=Product&edit=metafields.custom.location`
3. This will open a spreadsheet-like view of all your products with a column for "Location."

## Step 3: Paste Your Coordinates
Since you have the `geocoded_titles.csv`, you can now fill in the fields.

1. Open your `geocoded_titles.csv` file.
2. Filter or sort so you can see only the products that have coordinates in the `Location Metafield` column.
3. You can manually copy the `lat,lng` values and paste them into the corresponding rows in the Shopify Bulk Editor.
4. **Tip**: If you have many products, use the Search bar in the Bulk Editor to find specific products from your list.
5. Click **Save** in the top right of the Bulk Editor when finished.

---

## Step 4: Verify on the Map
Once you've saved at least one or two coordinates:
1. Go to your store's Theme Customizer.
2. Add the **Product Map** section to a page.
3. If everything is set up correctly, the pins should appear automatically!
