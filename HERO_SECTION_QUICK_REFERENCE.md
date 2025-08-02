# Dynamic Hero Section - Quick Reference

## 🎯 What It Does

**Product Pages**: Automatically uses product metafields for unique hero content per product  
**Static Pages**: Uses theme editor for manually managed hero content  

## 📋 Implementation Checklist

### ✅ Step 1: Upload Section
- [ ] Upload `dynamic-hero-section.liquid` to theme sections
- [ ] Section appears in theme editor as "Dynamic Hero Section"

### ✅ Step 2: Product Pages Setup
- [ ] Create metafield: `custom.hero_content` (JSON type)
- [ ] Add section to product template
- [ ] Configure product-specific content via metafields

### ✅ Step 3: Static Pages Setup
- [ ] Add section to desired pages via theme editor
- [ ] Configure content blocks for each slide
- [ ] Set section-wide settings (alignment, auto-slide, etc.)

## 🔧 Metafield Structure

```json
[
  {
    "content_type": "image",
    "desktop_image": "shopify://shop_images/desktop.jpg",
    "mobile_image": "shopify://shop_images/mobile.jpg",
    "heading": "Product Title",
    "text": "Product description",
    "btn_text": "Shop Now",
    "btn_url": "/products/product-handle"
  }
]
```

## 📱 Content Specifications

| Type | Desktop | Mobile |
|------|---------|--------|
| **Images** | 1920x1080px | 768x1024px |
| **Videos** | MP4, 1920x1080px | MP4, 768x1024px |
| **File Size** | < 500KB | < 300KB |

## 🎨 Available Features

- ✅ Images & Videos
- ✅ Carousel/Slider
- ✅ Mobile Responsive
- ✅ Auto-play Videos
- ✅ Keyboard Navigation
- ✅ Touch Gestures
- ✅ Performance Optimized
- ✅ SEO Friendly

## 🚀 Quick Start

1. **For Product Pages**: Set up metafields → Add section → Content appears automatically
2. **For Static Pages**: Add section → Configure blocks → Content managed via editor

## 📞 Need Help?

- Check `DYNAMIC_HERO_SETUP_GUIDE.md` for detailed instructions
- Verify metafield structure matches JSON example
- Test on both desktop and mobile devices 