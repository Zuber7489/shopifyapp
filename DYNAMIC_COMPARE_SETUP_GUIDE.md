# Dynamic Compare Bags Setup Guide

## Overview
This guide explains how to set up dynamic product data for the compare bags functionality using Shopify metafields and product tags.

## 🎯 **What's Now Dynamic**

### ✅ **Specs (Specifications)**
- **Capacity**: Product capacity (e.g., "20L", "24L")
- **Dimensions**: Product dimensions (e.g., "19\" x 15\" x 4\"")
- **Weight**: Product weight (e.g., "2.5lbs")

### ✅ **Features**
- Water bottle pocket
- Laptop pocket
- Trolley sleeve
- Carry-on size
- Phone pocket
- Hidden passport pocket
- Waterproof
- Zippers
- Tech caddy

### ✅ **Fabric & Tech Specs**
- **Fabric Type**: Material description
- **Silicon Face Coating**: Technical specifications
- **Coal PU Backside**: Waterproofing details

### ✅ **Overview**
- Product description and aesthetic details

### ✅ **Colors**
- Available color variants
- Dynamic color display

## 🛠 **Setup Instructions**

### **Option 1: Using Metafields (Recommended)**

#### **Step 1: Create Metafields in Shopify Admin**

Go to **Settings > Custom data > Metafields** and create these metafields:

**For Products:**
```
Namespace: custom
Key: capacity
Type: Single line text
Description: Product capacity (e.g., "20L", "24L")

Namespace: custom
Key: dimensions
Type: Single line text
Description: Product dimensions (e.g., "19\" x 15\" x 4\"")

Namespace: custom
Key: weight
Type: Single line text
Description: Product weight (e.g., "2.5lbs")

Namespace: custom
Key: fabric
Type: Single line text
Description: Fabric type (e.g., "420D Cordura Polycarbonate Nylon")

Namespace: custom
Key: features
Type: List of single line text
Description: Product features (comma-separated)

Namespace: custom
Key: silicon_coating
Type: Multi-line text
Description: Silicon face coating description

Namespace: custom
Key: coal_pu_coating
Type: Multi-line text
Description: Coal PU backside description

Namespace: custom
Key: overview
Type: Multi-line text
Description: Product overview and aesthetic description
```

#### **Step 2: Fill Metafields for Each Product**

For each product, add the metafield values:

**Example for Commuter Pack 20L:**
```
Capacity: 20L
Dimensions: 19" x 15" x 4"
Weight: 2.5lbs
Fabric: 420D Cordura Polycarbonate Nylon
Features: Water Bottle Pocket, Laptop Pocket, Trolley Sleeve, Carry-On Size, Phone Pocket, Waterproof, Zippers, Tech Caddy
Silicon Coating: Provides extreme weather, strain abrasion resistance without changing the look and hand feel of the fabric.
Coal PU Coating: Makes the fabric waterproof and also weldable which allows the seams of the bag to be bonded for additional weather resistance.
Overview: Has a modern technical aesthetic with a smooth supple feel. Has slightly more structure than our ballistic version, without being stiff and rigid like many PU and TPU coated fabrics. It's the ideal choice for adventure enthusiast that want a hybrid option to transition between office and outdoors.
```

**Example for Commuter Pack 24L:**
```
Capacity: 24L
Dimensions: 19" x 15" x 4"
Weight: 2.5lbs
Fabric: 840D Cordura Ballistic Nylon
Features: Water Bottle Pocket, Laptop Pocket, Trolley Sleeve, Carry-On Size, Phone Pocket, Hidden Passport Pocket, Waterproof, Zippers, Tech Caddy
Silicon Coating: Provides extreme weather, strain abrasion resistance without changing the look and hand feel of the fabric.
Coal PU Coating: Makes the fabric waterproof and also weldable which allows the seams of the bag to be bonded for additional weather resistance.
Overview: A timeless aesthetic and classic ballistic hand feel that has a fine grid-like texture that's subtly slick to the touch. It strikes the perfect balance to maintain some structure to prevent that floppy saggin look, while not being stiff and rigid. It's the ideal choice for purists seeking a refined, ultra-lux look that's office appropriate.
```

### **Option 2: Using Product Tags (Alternative)**

If you prefer using tags, add these tags to your products:

**For Features:**
- `water-bottle-pocket`
- `laptop-pocket`
- `trolley-sleeve`
- `carry-on`
- `phone-pocket`
- `passport-pocket`
- `waterproof`
- `zippers`
- `tech-caddy`

**For Specs:**
- `capacity-20L`
- `capacity-24L`
- `dimensions-19x15x4`
- `weight-2.5lbs`
- `fabric-420d-cordura`
- `fabric-840d-ballistic`

## 🔧 **Advanced Configuration**

### **Custom Collection for Comparison**

Create a specific collection for products that should appear in the compare modal:

1. Go to **Products > Collections**
2. Create a new collection called "Compare Bags"
3. Add the products you want to compare
4. Update the snippet to use this collection:

```liquid
{% assign compare_collection = collections['compare-bags'] %}
```

### **Dynamic Color Mapping**

To show actual color swatches, create a color mapping metafield:

```
Namespace: custom
Key: color_swatches
Type: List of single line text
Description: Color hex codes (e.g., "#000000,#1a2c2c,#666666")
```

Then update the JavaScript to use these colors:

```javascript
// In the colors generation section
const colorSwatches = prod.colorSwatches ? prod.colorSwatches.split(',') : ['#000000'];
const colorsHtml = colorSwatches.map(color => 
  `<div class="compare-modal-color" style="background-color: ${color.trim()}"></div>`
).join('');
```

### **Fabric-Specific Comparison**

For fabric comparison, you can create separate tabs or sections:

```javascript
function renderFabricComparison() {
  const fabricData = products.map(prod => ({
    fabric: prod.fabric,
    techSpecs: prod.techSpecs,
    overview: prod.overview
  }));
  
  // Render fabric-specific comparison
}
```

## 📊 **Data Structure Examples**

### **Complete Product Data Example**

```json
{
  "id": 123456789,
  "title": "Commuter Pack 20L",
  "image": "https://cdn.shopify.com/...",
  "price": "$229.00",
  "url": "/products/commuter-pack-20l",
  "isCurrentProduct": true,
  "capacity": "20L",
  "dimensions": "19\" x 15\" x 4\"",
  "weight": "2.5lbs",
  "fabric": "420D Cordura Polycarbonate Nylon",
  "features": [
    "Water Bottle Pocket",
    "Laptop Pocket", 
    "Trolley Sleeve",
    "Carry-On Size",
    "Phone Pocket",
    "Waterproof",
    "Zippers",
    "Tech Caddy"
  ],
  "techSpecs": {
    "siliconCoating": "Provides extreme weather, strain abrasion resistance without changing the look and hand feel of the fabric.",
    "coalPUCoating": "Makes the fabric waterproof and also weldable which allows the seams of the bag to be bonded for additional weather resistance."
  },
  "overview": "Has a modern technical aesthetic with a smooth supple feel...",
  "colors": ["Black", "Navy", "Grey"]
}
```

## 🧪 **Testing Checklist**

After setup, test these scenarios:

- [ ] Compare modal opens correctly
- [ ] All product data displays properly
- [ ] Specs show correct values
- [ ] Features list is accurate
- [ ] Fabric information is correct
- [ ] Tech specs are displayed
- [ ] Overview text is shown
- [ ] Colors/variants are accurate
- [ ] Related products load correctly
- [ ] Tab switching works (Product vs On model)
- [ ] Mobile responsiveness is maintained
- [ ] Modal closes properly

## 🔄 **Maintenance**

### **Adding New Products**
1. Add the product to your compare collection
2. Fill in all required metafields
3. Add appropriate tags if using tag-based system
4. Test the comparison functionality

### **Updating Product Data**
1. Update metafields in Shopify admin
2. Changes will automatically reflect in the compare modal
3. No code changes required

### **Adding New Features**
1. Add new metafield or tag
2. Update the JavaScript to handle the new data
3. Test with existing products

## 🚀 **Performance Optimization**

- The snippet uses efficient Liquid loops
- Product data is loaded once and cached
- Images are optimized with Shopify's CDN
- Minimal DOM manipulation for better performance

This setup provides a fully dynamic, maintainable compare bags functionality that automatically updates when you modify product data in Shopify! 