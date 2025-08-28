# Custom Text Below Add to Bag - Setup Guide

## Overview
This feature adds a new metafield `text_below_add_to_bag` that displays custom text below the Add to Bag button. Perfect for shipping notes, pre-order information, sales messages, or any variant-specific messaging.

## Features
- ✅ **Variant-specific**: Text can be different for each product variant (e.g., only show for 20L Carbonate if pre-order)
- ✅ **Site-wide color customization**: Easy to change colors across the entire site
- ✅ **Conditional display**: Only shows when metafield has content
- ✅ **Responsive design**: Optimized for both desktop and mobile
- ✅ **Professional styling**: Includes arrow icon and proper spacing

## 1. Metafield Setup

### Create the Metafield
1. Go to **Settings > Custom data > Metafields**
2. Click **Add definition**
3. Configure as follows:

**Basic Settings:**
- **Name**: `Text below Add to Bag`
- **Namespace**: `custom`
- **Key**: `text_below_add_to_bag`
- **Type**: `Single line text`
- **Description**: `Custom text to display below the Add to Bag button (shipping notes, pre-order info, etc.)`

**Target:**
- **Target**: `Product variants` (for variant-specific text)
- **Target**: `Products` (for product-level fallback)

**Validation:**
- **Minimum length**: `1`
- **Maximum length**: `200`

### Add Content to Products
1. Go to any product
2. Scroll to **Metafields** section
3. Add your custom text (e.g., "Pre-orders ship end of August")
4. Save the product

## 2. Color Customization

### Method 1: CSS Variables (Recommended)
Add this CSS to your theme's **Custom CSS** section:

```css
:root {
  --custom-text-color: #ff6600;  /* Orange (default) */
}
```

**Available Color Options:**
- `#ff6600` - Orange (default)
- `#000000` - Black
- `#28a745` - Green
- `#dc3545` - Red
- `#007bff` - Blue
- `#6f42c1` - Purple
- `#fd7e14` - Dark Orange

### Method 2: Direct CSS Override
Override the specific class in your theme's **Custom CSS**:

```css
.custom-text-below-add-to-bag .custom-text-content {
  color: #28a745 !important;  /* Green */
}

.custom-text-below-add-to-bag .custom-text-arrow svg {
  stroke: #28a745 !important;  /* Green arrow */
}
```

## 3. Usage Examples

### Pre-order Information
```
Metafield: "Pre-orders ship end of August"
```

### Shipping Notes
```
Metafield: "Free shipping on orders over $100"
```

### Sales Messages
```
Metafield: "Limited time offer - 20% off"
```

### Variant-Specific Messages
- **20L Carbonate**: "Pre-orders ship end of August"
- **24L Carbonate**: "In stock - ships next business day"
- **20L X-Pac**: "Backordered - ships in 2 weeks"

## 4. Technical Details

### Files Modified
- `snippets/custom-text-below-add-to-bag.liquid` - New snippet
- `product-template.liquid` - Integration points

### CSS Classes
- `.custom-text-below-add-to-bag` - Main container
- `.custom-text-arrow` - Arrow icon container
- `.custom-text-content` - Text content

### Responsive Breakpoints
- **Desktop**: 14px font, 16px arrow
- **Mobile**: 13px font, 14px arrow

## 5. Troubleshooting

### Text Not Displaying
1. Check if metafield has content
2. Verify metafield namespace/key is correct
3. Check browser console for errors

### Color Not Changing
1. Ensure CSS is added to theme's Custom CSS
2. Check CSS specificity (use `!important` if needed)
3. Clear browser cache

### Spacing Issues
1. Check if Feature Highlights section has proper margin
2. Verify responsive CSS is working
3. Test on different screen sizes

## 6. Advanced Customization

### Custom Arrow Icon
Replace the SVG in the snippet with your own icon:

```liquid
<div class="custom-text-arrow">
  <!-- Your custom icon here -->
</div>
```

### Animation Effects
Add hover effects in your CSS:

```css
.custom-text-below-add-to-bag:hover {
  transform: translateY(-2px);
  transition: transform 0.3s ease;
}
```

### Multiple Text Lines
For multi-line text, change the metafield type to `Multi-line text` and update the snippet accordingly.

## 7. Performance Notes

- Metafield content is rendered server-side
- No additional JavaScript required
- Minimal impact on page load time
- Responsive design with CSS-only animations

## 8. Support

For technical support or customization requests, refer to your development team or theme documentation.

---

**Last Updated**: [Current Date]
**Version**: 1.0
**Compatibility**: Shopify 2.0 themes, Liquid templates 