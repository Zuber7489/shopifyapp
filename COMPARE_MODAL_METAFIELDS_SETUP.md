# Compare Bags Modal - Metafields Setup Guide

This guide explains all the metafields that need to be configured for the enhanced compare bags modal functionality.

## Overview

The compare bags modal now supports:
- **Variant-based images**: Each variant can have its own image
- **Custom product titles**: Each variant can have a custom title
- **Configurable 90-degree left labels**: All category labels can be customized
- **Configurable golden labels**: All spec value labels can be customized

## Required Metafields

### 1. Product Title Metafield
- **Namespace**: `custom`
- **Key**: `comparebag_product_title`
- **Type**: `single_line_text_field` or `rich_text`
- **Description**: Custom title for the product variant in the compare modal
- **Default**: Product title + variant option

### 2. Variant Image Metafield
- **Namespace**: `custom`
- **Key**: `comparebag_variant_image`
- **Type**: `file_reference`
- **Description**: Custom image for the product variant in the compare modal
- **Default**: Variant's default image or product featured image
- **Note**: Client can upload images directly through Shopify's file picker

### 3. Custom Price Metafield
- **Namespace**: `custom`
- **Key**: `comparebag_custom_price`
- **Type**: `single_line_text_field`
- **Description**: Custom price for the product variant in the compare modal
- **Default**: Variant's default price
- **Note**: Client can enter any price format (e.g., "Rs. 12,400.00", "$129.99", "€89.50")

### 4. 90-Degree Left Labels (Category Labels)

#### Specs Label
- **Namespace**: `custom`
- **Key**: `comparebag_specs_label`
- **Type**: `single_line_text_field`
- **Description**: Label for the Specs section (90-degree rotated)
- **Default**: "Specs"

#### Features Label
- **Namespace**: `custom`
- **Key**: `comparebag_features_label`
- **Type**: `single_line_text_field`
- **Description**: Label for the Features section (90-degree rotated)
- **Default**: "Features"

#### Available In Label
- **Namespace**: `custom`
- **Key**: `comparebag_available_in_label`
- **Type**: `single_line_text_field`
- **Description**: Label for the Available In section (90-degree rotated)
- **Default**: "Available in"

#### Fabric Label
- **Namespace**: `custom`
- **Key**: `comparebag_fabric_label`
- **Type**: `single_line_text_field`
- **Description**: Label for the Fabric section (90-degree rotated)
- **Default**: "Fabric"

#### Tech Specs Label
- **Namespace**: `custom`
- **Key**: `comparebag_tech_specs_label`
- **Type**: `single_line_text_field`
- **Description**: Label for the Tech Specs section (90-degree rotated)
- **Default**: "Tech Specs"

#### Overall Difference Label
- **Namespace**: `custom`
- **Key**: `comparebag_overall_difference_label`
- **Type**: `single_line_text_field`
- **Description**: Label for the Overall Difference section (90-degree rotated)
- **Default**: "Overall Difference"

### 5. Golden Labels (Under Spec Values)

#### Capacity Label
- **Namespace**: `custom`
- **Key**: `comparebag_capacity_label`
- **Type**: `single_line_text_field`
- **Description**: Golden label under capacity value
- **Default**: "Capacity"

#### Dimensions Label
- **Namespace**: `custom`
- **Key**: `comparebag_dimensions_label`
- **Type**: `single_line_text_field`
- **Description**: Golden label under dimensions value
- **Default**: "Dimensions"

#### Weight Label
- **Namespace**: `custom`
- **Key**: `comparebag_weight_label`
- **Type**: `single_line_text_field`
- **Description**: Golden label under weight value
- **Default**: "Weight"

#### Price Label
- **Namespace**: `custom`
- **Key**: `comparebag_price_label`
- **Type**: `single_line_text_field`
- **Description**: Golden label under price value
- **Default**: "Price"

### 6. Existing Metafields (Enhanced)

#### Product Data Metafields
- **Capacity**: `custom.capacity` (rich_text)
- **Dimensions**: `custom.dimensions` (rich_text)
- **Weight**: `custom.weight` (rich_text)
- **Fabric**: `custom.fabric` (rich_text)
- **Features**: `custom.features` (rich_text)
- **Tech Specs**: `custom.tech_specs` (rich_text)
- **Overview**: `custom.overview` (rich_text)

## Required Metafields Summary

### **New Metafields to Create:**
1. `custom.comparebag_product_title` - Custom product title
2. `custom.comparebag_variant_image` - Custom variant image URL
3. `custom.comparebag_custom_price` - Custom variant price
4. `custom.comparebag_specs_label` - Specs section label
5. `custom.comparebag_features_label` - Features section label
6. `custom.comparebag_available_in_label` - Available in section label
7. `custom.comparebag_fabric_label` - Fabric section label
8. `custom.comparebag_tech_specs_label` - Tech specs section label
9. `custom.comparebag_overall_difference_label` - Overall difference section label
10. `custom.comparebag_capacity_label` - Capacity golden label
11. `custom.comparebag_dimensions_label` - Dimensions golden label
12. `custom.comparebag_weight_label` - Weight golden label
13. `custom.comparebag_price_label` - Price golden label

### **Existing Metafields (Enhanced):**
- `custom.comparebag_capacity` - Product capacity
- `custom.comparebag_dimensions` - Product dimensions
- `custom.comparebag_weight` - Product weight
- `custom.comparebag_fabric` - Fabric type
- `custom.comparebag_features` - Product features
- `custom.comparebag_tech_specs` - Technical specifications
- `custom.comparebag_overview` - Product overview

## Setup Instructions

### Step 1: Create Metafields in Shopify Admin

1. Go to **Settings > Custom data > Metafields**
2. Select **Products** as the resource
3. Create each metafield with the specifications above

### Step 2: Configure Metafields for Each Variant

1. Go to a product with variants
2. Click on each variant
3. Scroll down to **Metafields** section
4. Fill in the values for each metafield

### Step 3: Upload Variant Images

1. In the variant settings, ensure each variant has its own image
2. The modal will automatically use the variant-specific image

## Example Configuration

### For a Tote Bag Variant:

**Product Title**: "All Terrain Tote - Large"
**Specs Label**: "Specifications"
**Features Label**: "Key Features"
**Available In Label**: "Color Options"
**Fabric Label**: "Material"
**Tech Specs Label**: "Technical Details"
**Overall Difference Label**: "Product Overview"

**Capacity Label**: "Volume"
**Dimensions Label**: "Size"
**Weight Label**: "Mass"
**Price Label**: "Cost"

## Technical Notes

### Image Handling
- The modal prioritizes `custom.comparebag_variant_image` metafield (file_reference type) for variant-specific images
- Falls back to `variant.image` from the JSON data
- Falls back to `product.featured_image` if no variant image is available
- Images are automatically resized to 300x300 resolution
- Client can upload images directly through Shopify's file picker interface

### Rich Text Support
- All text metafields support rich text formatting
- HTML entities are automatically decoded
- Bold, italic, and other formatting is preserved

### Fallback Values
- If a metafield is not set, the system uses default values
- This ensures the modal always displays properly

### Dynamic Updates
- When variants are changed on the product page, the modal updates automatically
- All labels and content refresh based on the selected variant

## Troubleshooting

### Modal Not Showing Correct Images
1. Ensure each variant has its own image uploaded
2. Check that `window.productMetafieldsData` contains variant image data
3. Verify the image URLs are accessible

### Labels Not Updating
1. Check that metafields are properly configured
2. Ensure metafield namespaces and keys match exactly
3. Clear browser cache and refresh the page

### Rich Text Not Rendering
1. Verify metafields are set to `rich_text` type
2. Check that the JSON data includes the rich text content
3. Ensure the `parseRichText` function is working correctly

## Support

For technical support or questions about this implementation, refer to the main documentation or contact the development team. 