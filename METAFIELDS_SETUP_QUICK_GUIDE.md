# 🚀 Quick Metafields Setup Guide

## ⚠️ **Current Issue**
The compare modal is not working because the required metafields don't exist yet. Follow this guide to create them.

---

## 📋 **Required Metafields (Create These Now)**

### **Step 1: Go to Shopify Admin**
1. Go to **Settings** > **Custom data** > **Products**
2. Click **Add definition**

### **Step 2: Create These 7 Metafields**

| **Metafield Name** | **Type** | **Description** | **Example Value** |
|-------------------|----------|-----------------|-------------------|
| `capacity` | Rich text editor | Product capacity/size | `20L` |
| `dimensions` | Rich text editor | Product dimensions | `19" x 18" x 4"` |
| `weight` | Rich text editor | Product weight | `2.5lbs` |
| `fabric` | Rich text editor | Fabric description | `420D Cordura Polycarbonate Nylon` |
| `features` | Rich text editor | Product features | `Water bottle pocket, Luggage pass through, Laptop compartment, Carry handle, Water proof, Zippers, Tech caddy` |
| `tech_specs` | Rich text editor | Technical specifications | `Silicon Face Coating: This coating provides extreme weather, strain abrasion resistance without changing the look and hand feel of the fabric. Coal PU Backside: This coating makes the fabric waterproof and also weldable which allows the seams of the bag to be bonded for additional weather resistance.` |
| `overview` | Rich text editor | Product overview | `Modern technical aesthetic with a smooth supple feel. More structure than our ballistic version, ideal for adventure enthusiasts that want a hybrid option to transition between office and outdoors.` |

---

## 🎯 **Quick Setup Steps**

### **1. Create Metafields**
- Go to **Settings** > **Custom data** > **Products**
- Click **Add definition** 7 times
- Create each metafield with the exact names above
- Set all to **Rich text editor** type

### **2. Add Content to Products**
- Go to any product
- Scroll down to **Metafields** section
- Fill in the values for each metafield
- Save the product

### **3. Test the Compare Modal**
- Go to a product page
- Click **Compare bags** button
- Modal should now work without errors

---

## 🔧 **Variant Setup (Optional)**

For size and fabric comparison to work:

### **Size Variants**
Create variants with size in Option 1:
- Commuter Pack 20L
- Commuter Pack 24L
- Commuter Pack 30L

### **Fabric Variants**
Create variants with fabric in Option 2:
- Commuter Pack 20L Carbonate
- Commuter Pack 20L Ballistic Nylon

---

## ✅ **After Setup**

Once you create these metafields and add content:

1. **Compare modal will work** without JavaScript errors
2. **Size comparison** will show different sizes
3. **Fabric comparison** will show different fabrics
4. **Dynamic content** will display from metafields

---

## 🆘 **If Still Not Working**

1. **Clear browser cache** and refresh
2. **Check metafield names** are exactly as shown
3. **Ensure metafields have content** (not empty)
4. **Check browser console** for any remaining errors

---

## 📝 **Example Product Setup**

**Product**: Commuter Pack 20L

**Metafields**:
- `capacity`: 20L
- `dimensions`: 19" x 18" x 4"
- `weight`: 2.5lbs
- `fabric`: 420D Cordura Polycarbonate Nylon
- `features`: Water bottle pocket, Luggage pass through, Laptop compartment, Carry handle, Water proof, Zippers, Tech caddy
- `tech_specs`: Silicon Face Coating: This coating provides extreme weather, strain abrasion resistance without changing the look and hand feel of the fabric. Coal PU Backside: This coating makes the fabric waterproof and also weldable which allows the seams of the bag to be bonded for additional weather resistance.
- `overview`: Modern technical aesthetic with a smooth supple feel. More structure than our ballistic version, ideal for adventure enthusiasts that want a hybrid option to transition between office and outdoors.

**Result**: Compare modal will work perfectly! 🚀 