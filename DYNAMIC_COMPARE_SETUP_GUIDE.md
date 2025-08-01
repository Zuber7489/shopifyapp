# 🎯 Dynamic Compare Bags Setup Guide (Updated for New UI)

## 📋 **New UI Features:**
- **Two Tabs**: "Size" and "Fabric" comparison views
- **Clean Layout**: 2-column grid comparing current product with variants
- **Rich Content**: Support for formatted text from richtext editors
- **Combined Tech Specs**: Single metafield for all technical specifications
- **Size Comparison**: Compare different sizes of the same product
- **Fabric Comparison**: Compare different fabric options of the same product

---

## 🔧 **Shopify Metafields Setup**

### **1. Required Metafields (All Rich Text Editor Type)**

Go to **Settings > Custom data > Products > Add definition** and create these metafields:

| **Metafield Name** | **Type** | **Description** | **Example Content** |
|-------------------|----------|-----------------|-------------------|
| `capacity` | Rich text editor | Product capacity/size | `20L` |
| `dimensions` | Rich text editor | Product dimensions | `19" x 18" x 4"` |
| `weight` | Rich text editor | Product weight | `2.5lbs` |
| `fabric` | Rich text editor | Fabric/material description | `420D Cordura Polycarbonate Nylon` |
| `features` | Rich text editor | Product features (comma-separated) | `Water bottle pocket, Luggage pass through, Laptop compartment, Carry handle, Water proof, Zippers, Tech caddy` |
| `tech_specs` | Rich text editor | **Combined tech specs** (both silicon coating & coal PU) | `Silicon Face Coating: This coating provides extreme weather, strain abrasion resistance without changing the look and hand feel of the fabric. Coal PU Backside: This coating makes the fabric waterproof and also weldable which allows the seams of the bag to be bonded for additional weather resistance.` |
| `overview` | Rich text editor | Product overview/description | `Modern technical aesthetic with a smooth supple feel. More structure than our ballistic version, ideal for adventure enthusiasts that want a hybrid option to transition between office and outdoors.` |

### **2. Variant-Specific Metafields (Optional)**

For more detailed size-specific information, you can also create variant-level metafields:

| **Metafield Name** | **Type** | **Scope** | **Description** |
|-------------------|----------|-----------|-----------------|
| `dimensions` | Rich text editor | Variant | Size-specific dimensions |
| `weight` | Rich text editor | Variant | Size-specific weight |
| `features` | Rich text editor | Variant | Size-specific features |
| `tech_specs` | Rich text editor | Variant | Size-specific tech specs |
| `overview` | Rich text editor | Variant | Size-specific overview |

**Note**: If variant-level metafields are not set, the system will fall back to product-level metafields.

### **3. Fabric Variants Setup**

For fabric comparison to work, create product variants with fabric options:

**Variant Structure:**
- **Option 1**: Size (20L, 24L, 30L, etc.)
- **Option 2**: Fabric (Carbonate, Ballistic Nylon, Cordura, etc.)

**Example Variants:**
- Commuter Pack 20L Carbonate
- Commuter Pack 20L Ballistic Nylon
- Commuter Pack 24L Carbonate
- Commuter Pack 24L Ballistic Nylon

**Fabric Detection**: The system automatically detects fabric variants by looking for:
- `option2` containing "Fabric", "fabric", "Carbonate", "Ballistic", "Nylon", "Cordura"

---

## 🎨 **UI Tab Structure**

### **Size Tab Content:**
- Product image
- Product title (with size variant)
- **Specs**: Capacity, Dimensions, Weight
- **Features**: List of product features
- **Available in**: Color swatches
- **Price**: Product price
- **Add to Bag/Select Size**: Action buttons

### **Fabric Tab Content:**
- Product image
- Product title (with fabric variant)
- **Fabric**: Material description
- **Tech Specs**: Combined technical specifications
- **Overview**: Product overview/description
- **Available in**: Color swatches
- **Price**: Product price
- **Add to Bag/Select Fabric**: Action buttons

---

## 📝 **Content Examples**

### **Example: Commuter Pack Size Variants**

**Current Product (20L):**
```
capacity: 20L
dimensions: 19" x 18" x 4"
weight: 2.5lbs
fabric: 420D Cordura Polycarbonate Nylon
features: Water bottle pocket, Luggage pass through, Laptop compartment, Carry handle, Water proof, Zippers, Tech caddy
tech_specs: Silicon Face Coating: This coating provides extreme weather, strain abrasion resistance without changing the look and hand feel of the fabric. Coal PU Backside: This coating makes the fabric waterproof and also weldable which allows the seams of the bag to be bonded for additional weather resistance.
overview: Modern technical aesthetic with a smooth supple feel. More structure than our ballistic version, ideal for adventure enthusiasts that want a hybrid option to transition between office and outdoors.
```

**Size Variant (24L):**
```
capacity: 24L
dimensions: 19" x 15" x 4"
weight: 2.5lbs
fabric: 420D Cordura Polycarbonate Nylon
features: Water bottle pocket, Luggage pass through, Laptop compartment, Carry handle, Water proof, Zippers, Tech caddy, Hidden passport pocket
tech_specs: Silicon Face Coating: This coating provides extreme weather, strain abrasion resistance without changing the look and hand feel of the fabric. Coal PU Backside: This coating makes the fabric waterproof and also weldable which allows the seams of the bag to be bonded for additional weather resistance.
overview: Modern technical aesthetic with a smooth supple feel. More structure than our ballistic version, ideal for adventure enthusiasts that want a hybrid option to transition between office and outdoors.
```

**Note**: The compare modal will show:
- **Size Tab**: Current product (e.g., 20L) compared with its size variants (e.g., 24L, 30L, etc.)
- **Fabric Tab**: Current product compared with its fabric variants (e.g., Carbonate, Ballistic Nylon, etc.)

---

## 🎯 **Benefits of New Structure**

### **✅ Rich Text Editor Advantages:**
- **Formatting Control**: Admins can use bold, italic, lists, etc.
- **Better Content**: More professional and readable content
- **Flexibility**: Easy to update and maintain
- **HTML Support**: Can include links, formatting, etc.

### **✅ Combined Tech Specs:**
- **Simplified Management**: One field instead of two
- **Better Organization**: All tech specs in one place
- **Easier Updates**: Single field to maintain
- **Consistent Formatting**: Uniform presentation

### **✅ New UI Benefits:**
- **Cleaner Design**: Better visual hierarchy
- **Tabbed Interface**: Organized content presentation
- **Responsive**: Works well on all devices
- **Professional Look**: Matches modern design standards

---

## 🚀 **Implementation Steps**

1. **Create Metafields**: Set up all 7 metafields as rich text editors
2. **Add Content**: Populate metafields for each product
3. **Test Functionality**: Verify compare modal works correctly
4. **Style Adjustments**: Fine-tune CSS if needed
5. **Content Review**: Ensure all content displays properly

---

## 🔍 **Testing Checklist**

- [ ] Compare button appears on product page
- [ ] Modal opens correctly
- [ ] Size tab shows specs and features
- [ ] Fabric tab shows fabric, tech specs, and overview
- [ ] Content displays with proper formatting
- [ ] Mobile responsiveness works
- [ ] Tab switching functions properly
- [ ] Close button and escape key work
- [ ] Add to Bag/Shop Now buttons function

---

## 💡 **Pro Tips**

1. **Content Strategy**: Use consistent formatting across all products
2. **Feature Lists**: Keep feature lists concise and scannable
3. **Tech Specs**: Use clear, technical language for specifications
4. **Overview**: Write compelling, benefit-focused descriptions
5. **Regular Updates**: Keep content fresh and accurate

---

## 🆘 **Troubleshooting**

**Issue**: Content not displaying
- **Solution**: Check metafield names match exactly (case-sensitive)

**Issue**: Formatting not showing
- **Solution**: Ensure metafields are set to "Rich text editor" type

**Issue**: Modal not opening
- **Solution**: Check browser console for JavaScript errors

**Issue**: Mobile layout issues
- **Solution**: Test on actual mobile devices, not just browser dev tools 