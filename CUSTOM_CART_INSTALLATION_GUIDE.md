# 🛒 Custom Cart Installation Guide

## ✅ **What You Got Now**

Your custom cart file `snippets/custom-cart-complete.liquid` is **ready to use** and matches the screenshot design perfectly!

## 🚀 **Quick Installation (3 Steps)**

### 1. **Add to Theme.liquid**
Add this line in your `theme.liquid` file, right after the `<div id="page">` opening tag:

```liquid
{% render 'custom-cart-complete' %}
```

### 2. **Add Cart Toggle Buttons**
Update your existing cart buttons with `data-cart-toggle`:

```html
<!-- Replace your existing cart buttons with: -->
<button data-cart-toggle>🛒 Cart</button>
<button data-cart-toggle>🛒</button>
```

### 3. **Update Cart Count Displays**
Add `data-cart-count` to your cart count elements:

```html
<!-- Replace your existing cart count displays with: -->
<span data-cart-count>{{ cart.item_count }}</span>
```

## 🎯 **Features That Match Screenshot**

✅ **Free Shipping Progress Bar** - With truck icon  
✅ **Cart Items** - Shows variant info, strikethrough prices, savings  
✅ **Bundle & Save Section** - Horizontal scrollable cards with variant dots  
✅ **Sticky Checkout** - Payment icons, clean layout  
✅ **Right-side Opening** - Slides in from right like UpCart  

## 🔧 **Bundle & Save Setup (Metafields)**

To show bundle recommendations, add this metafield to your products:

**Metafield Namespace:** `custom`  
**Metafield Key:** `bundle_recommendations`  
**Metafield Type:** `json`  
**Metafield Value Example:**
```json
[
  {
    "id": 123456789,
    "title": "Travel Organizer",
    "price": 2500,
    "compare_at_price": 3500,
    "image": "/products/travel-organizer.jpg",
    "variants": [
      {"id": 123456789, "title": "X-Pac"},
      {"id": 123456790, "title": "Carbonate"}
    ]
  }
]
```

## 🎨 **Customization**

- **Colors**: Update CSS variables in the `<style>` section
- **Free Shipping Threshold**: Set in theme settings or update `free_shipping_threshold` variable
- **Shipping Cost**: Update `shipping_cost` variable

## 🧪 **Testing**

1. Add products to cart
2. Click cart toggle button
3. Test quantity changes, remove items
4. Test bundle recommendations
5. Test checkout flow

## 🗑️ **Remove UpCart App**

After testing your custom cart:
1. Go to Shopify Apps
2. Uninstall UpCart
3. Remove any UpCart code from your theme

## 🆘 **Need Help?**

- Check browser console for errors
- Verify all `data-*` attributes are added
- Ensure metafields are properly formatted
- Test on different devices/screen sizes

---

**Your custom cart is now ready! 🎉** 