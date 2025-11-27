# Seed Data Guide

## Overview

I've created a Django management command to populate your database with sample food data and generated images for the burger ingredients.

## Generated Images

The following images have been generated and are available in the artifacts folder:

1. **burger_base** - Burger bun on a plate
2. **burger_patty** - Beef patty
3. **lettuce_leaf** - Fresh lettuce
4. **tomato_slice** - Tomato slice
5. **cheese_slice** - Cheese slice
6. **onion_rings** - Crispy onion rings
7. **bacon_strips** - Bacon strips

## Sample Data Structure

### Categories
- **Savory** - For burgers, pizzas, sandwiches
- **Sweets** - For desserts

### Food Types

#### 1. Classic Burger ($5.99)
**Default Ingredients:**
- Burger Bun (layer 1)
- Beef Patty (layer 2)

**Optional Toppings:**
- Lettuce (+$0.50, layer 3)
- Tomato (+$0.50, layer 4)
- Cheese (+$1.00, layer 5)
- Onion Rings (+$1.50, layer 6)
- Bacon (+$2.00, layer 7)

#### 2. Custom Pizza ($8.99)
**Default Ingredients:**
- Pizza Dough & Sauce (layer 1)
- Mozzarella Cheese (layer 2)

**Optional Toppings:**
- Pepperoni (+$1.50, layer 3)
- Mushrooms (+$1.00, layer 4)
- Black Olives (+$0.75, layer 5)
- Bell Peppers (+$0.75, layer 6)

#### 3. Deli Sandwich ($4.99)
**Default Ingredients:**
- Bread (layer 1)

**Optional Ingredients:**
- Turkey (+$2.00, layer 2)
- Ham (+$2.00, layer 3)
- Swiss Cheese (+$1.00, layer 4)
- Lettuce (+$0.50, layer 5)
- Tomato (+$0.50, layer 6)
- Mayonnaise (+$0.25, layer 7)
- Mustard (+$0.25, layer 8)

#### 4. Ice Cream Sundae ($3.99)
**Default Ingredients:**
- Vanilla Ice Cream (layer 1)

**Optional Toppings:**
- Chocolate Sauce (+$0.50, layer 2)
- Caramel Sauce (+$0.50, layer 3)
- Sprinkles (+$0.25, layer 4)
- Whipped Cream (+$0.50, layer 5)
- Cherry on Top (+$0.25, layer 6)

## Running the Seed Command

To populate your database with this sample data:

```cmd
cd custom_food_builder\backend
python manage.py seed_data
```

This will:
1. Clear existing food data (Categories, FoodTypes, Ingredients)
2. Create 2 categories
3. Create 4 food types
4. Create all ingredients with proper pricing and layer ordering

## Adding Images

### Option 1: Manual Upload via Admin
1. Run the seed command
2. Go to Django admin (`http://localhost:8000/admin`)
3. Upload images for each food type and ingredient

### Option 2: Use Generated Images
The generated images are in the artifacts folder. You can:
1. Download them from the artifacts
2. Upload via admin panel
3. Assign to appropriate food items

### Option 3: Use Placeholder URLs
For testing, you can use placeholder image services like:
- `https://via.placeholder.com/300x300/FF6B35/FFFFFF?text=Burger`
- `https://via.placeholder.com/300x300/F7931E/FFFFFF?text=Pizza`

## Image Quota Note

⚠️ **Image Generation Quota Exhausted**: I hit the image generation quota after creating 7 images. The quota will reset in approximately 5 hours. 

For now, you can:
1. Use the 7 generated images for the burger
2. Add placeholder images for other items
3. Upload your own images via admin
4. Wait for quota reset to generate more images

## Next Steps

1. Run migrations if you haven't already:
   ```cmd
   python manage.py makemigrations
   python manage.py migrate
   ```

2. Run the seed command:
   ```cmd
   python manage.py seed_data
   ```

3. Access admin panel and upload images for the items

4. Test the application with real data!
