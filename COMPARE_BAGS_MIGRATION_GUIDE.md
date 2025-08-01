# Compare Bags Migration Guide

## Overview
This guide explains how to migrate the compare bags functionality from the product template to separate snippets to avoid the 256kb limit.

## Files Created
1. `snippets/compare-bags-modal.liquid` - Contains the modal HTML, CSS, and JavaScript
2. `snippets/compare-bags-buttons.liquid` - Contains the compare buttons

## Migration Steps

### Step 1: Add the Modal Snippet
Add this line near the end of your `product-template.liquid` file, before the closing `</script>` tag:

```liquid
{% render 'compare-bags-modal' %}
```

### Step 2: Replace Compare Buttons
Replace the existing compare buttons in your product template with:

```liquid
{% render 'compare-bags-buttons' %}
```

### Step 3: Remove Old Code
Remove the following sections from your `product-template.liquid`:

#### Remove CSS (lines ~5230-5407):
```css
/* Remove this entire CSS block */
#compareBagsModalV2 {
  /* ... all modal styles ... */
}
```

#### Remove HTML Modal (lines ~5441-5466):
```html
<!-- Remove this entire modal HTML -->
<div id="compareBagsModalV2">
  <!-- ... all modal content ... -->
</div>
```

#### Remove JavaScript (lines ~5468-5603):
```javascript
/* Remove these functions */
function openCompareBagsModalV2() { /* ... */ }
function closeCompareBagsModalV2() { /* ... */ }
function switchCompareTab(tab) { /* ... */ }
function renderCompareBagsTable(tab) { /* ... */ }
// ... and all related JavaScript
```

#### Remove Button Styles (lines ~1211-1280):
```css
/* Remove these button styles */
.compare-btn-row { /* ... */ }
.comparemobilebtn { /* ... */ }
.comparedesktopbtn { /* ... */ }
```

### Step 4: Update Button Placements
Replace the existing button HTML with the snippet calls:

**For Mobile Button (around line 589):**
```liquid
<!-- Replace this: -->
<button class="comparemobilebtn" id="compareBtnMobile" ...>
  Compare bags
</button>

<!-- With this: -->
{% render 'compare-bags-buttons' %}
```

**For Desktop Button (around line 622):**
```liquid
<!-- Replace this: -->
<button id="compareBtnDesktop" class="comparedesktopbtn" ...>
  Compare bags
</button>

<!-- With this: -->
{% render 'compare-bags-buttons' %}
```

## Benefits
1. **Reduced File Size**: Moves ~400+ lines of code out of the main template
2. **Better Organization**: Separates concerns into logical snippets
3. **Reusability**: Can be used on other templates if needed
4. **Easier Maintenance**: Compare functionality is isolated and easier to update

## Testing
After migration:
1. Test the compare buttons work on both mobile and desktop
2. Verify the modal opens and closes properly
3. Check that all styling is preserved
4. Test the tab switching functionality
5. Verify mobile scroll lock works correctly

## Notes
- The snippets maintain all existing functionality
- All event listeners are properly initialized
- Mobile responsiveness is preserved
- The modal uses the same product data logic as before
- All CSS classes and IDs remain the same for compatibility

## Troubleshooting
If buttons don't work:
1. Ensure both snippets are rendered in the template
2. Check that the modal snippet is loaded before any button references
3. Verify no JavaScript errors in the console
4. Make sure the product template has access to the required Liquid variables 