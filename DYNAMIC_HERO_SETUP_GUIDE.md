# Dynamic Hero Section Setup Guide

## Overview

The Dynamic Hero Section is a flexible, reusable component that automatically adapts to different page types:

- **Product Pages**: Uses product metafields for dynamic, product-specific content
- **Static Pages**: Uses theme editor settings for manually managed content

## Features

✅ **Dual Mode Operation**: Automatically switches between metafield and theme editor content  
✅ **Multiple Content Types**: Images, videos, and carousels  
✅ **Responsive Design**: Optimized for desktop and mobile  
✅ **Performance Optimized**: Lazy loading, hardware acceleration, and efficient animations  
✅ **Accessibility**: Keyboard navigation, ARIA labels, and screen reader support  
✅ **SEO Friendly**: Proper alt tags, semantic HTML, and structured content  

## Implementation Steps

### 1. Add the Section to Your Theme

1. Upload the `dynamic-hero-section.liquid` file to your theme's sections directory
2. The section will be available in the theme editor under "Dynamic Hero Section"

### 2. Product Page Setup (Metafields)

#### A. Create Product Metafields

1. Go to **Settings > Custom data > Products**
2. Create a new metafield definition:
   - **Name**: Hero Content
   - **Namespace**: `custom`
   - **Key**: `hero_content`
   - **Type**: JSON
   - **Description**: Hero section content for product pages

#### B. Metafield JSON Structure

```json
[
  {
    "content_type": "image",
    "desktop_image": "shopify://shop_images/desktop_hero.jpg",
    "mobile_image": "shopify://shop_images/mobile_hero.jpg",
    "heading": "Product Hero Title",
    "text": "Product description or hero text",
    "btn_text": "Shop Now",
    "btn_url": "/products/product-handle",
    "mobile_padding_top": 50
  },
  {
    "content_type": "video",
    "desktop_video": "shopify://shop_files/hero_video.mp4",
    "mobile_video": "shopify://shop_files/hero_video_mobile.mp4",
    "video_poster": "shopify://shop_images/video_poster.jpg",
    "video_poster_mobile": "shopify://shop_images/video_poster_mobile.jpg",
    "autoplay": true,
    "loop": true,
    "muted": true,
    "controls": false,
    "heading": "Video Hero Title",
    "text": "Video hero description",
    "btn_text": "Learn More",
    "btn_url": "/pages/about",
    "mobile_padding_top": 40
  }
]
```

#### C. Add Section to Product Template

1. Go to **Online Store > Themes > Customize**
2. Navigate to a product page
3. Click **Add section**
4. Select **Dynamic Hero Section**
5. The section will automatically use product metafields

### 3. Static Page Setup (Theme Editor)

#### A. Add to Static Pages

1. Go to **Online Store > Themes > Customize**
2. Navigate to the desired page (homepage, about, etc.)
3. Click **Add section**
4. Select **Dynamic Hero Section**
5. Configure using the theme editor settings

#### B. Configure Section Settings

- **Text Alignment**: Left, Center, or Justified
- **Auto-Slide**: Enable/disable automatic slide rotation
- **Slide Interval**: Time between slides (3-10 seconds)

#### C. Add Content Blocks

For each slide, configure:

**Image Slides:**
- Desktop Image (1920x1080px recommended)
- Mobile Image (768x1024px recommended)
- Heading and text content
- Call-to-action button

**Video Slides:**
- Desktop Video URL (MP4 format)
- Mobile Video URL (optional)
- Poster images for desktop and mobile
- Video settings (autoplay, loop, mute, controls)
- Content and CTA

## Content Guidelines

### Image Specifications

**Desktop:**
- Resolution: 1920x1080px minimum
- Format: JPG, PNG, WebP
- File size: < 500KB for optimal performance

**Mobile:**
- Resolution: 768x1024px minimum
- Format: JPG, PNG, WebP
- File size: < 300KB for optimal performance

### Video Specifications

**Desktop:**
- Format: MP4 (H.264 codec)
- Resolution: 1920x1080px
- Bitrate: 2-4 Mbps
- Duration: 10-30 seconds recommended

**Mobile:**
- Format: MP4 (H.264 codec)
- Resolution: 768x1024px
- Bitrate: 1-2 Mbps
- Duration: 10-30 seconds recommended

### Content Best Practices

1. **Headings**: Keep under 60 characters for optimal display
2. **Descriptions**: 100-200 characters for best readability
3. **CTA Buttons**: Clear, action-oriented text (e.g., "Shop Now", "Learn More")
4. **Visual Hierarchy**: Ensure text is readable over background images/videos
5. **Brand Consistency**: Use consistent colors, fonts, and messaging

## Advanced Configuration

### Custom CSS Styling

You can customize the appearance by adding CSS to your theme's custom CSS section:

```css
/* Custom hero section styling */
.dynamic-hero-section {
  /* Your custom styles */
}

.hero-title {
  /* Custom title styling */
}

.hero-cta-button {
  /* Custom button styling */
}
```

### JavaScript Customization

The section includes event hooks for custom functionality:

```javascript
// Listen for slide changes
document.addEventListener('heroSlideChange', function(e) {
  console.log('Slide changed to:', e.detail.slideIndex);
});

// Listen for section initialization
document.addEventListener('heroSectionInit', function(e) {
  console.log('Hero section initialized');
});
```

## Troubleshooting

### Common Issues

**1. Metafields Not Showing**
- Verify metafield namespace is `custom` and key is `hero_content`
- Ensure metafield type is JSON
- Check that the JSON structure is valid

**2. Images Not Loading**
- Verify image URLs are correct
- Check file permissions
- Ensure images are uploaded to Shopify Files

**3. Videos Not Playing**
- Verify video format is MP4
- Check video URLs are accessible
- Ensure autoplay is enabled and video is muted

**4. Mobile Responsiveness Issues**
- Verify mobile-specific images/videos are provided
- Check CSS media queries
- Test on actual mobile devices

### Performance Optimization

1. **Image Optimization**
   - Use WebP format when possible
   - Compress images to reduce file size
   - Use appropriate image dimensions

2. **Video Optimization**
   - Compress videos to reduce file size
   - Use appropriate bitrates for quality/size balance
   - Consider using different videos for mobile/desktop

3. **Loading Performance**
   - Enable lazy loading for non-critical content
   - Use preload for first slide content
   - Minimize JavaScript execution time

## Support

For technical support or questions about implementation:

1. Check this guide for common solutions
2. Review the metafield JSON structure
3. Test with different content types
4. Contact your development team for custom modifications

## Version History

- **v1.0**: Initial release with dual-mode support
- Features: Product metafields, theme editor, responsive design, accessibility 