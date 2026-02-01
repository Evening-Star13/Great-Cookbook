# Great Cookbook

A comprehensive recipe management application built with React and IndexedDB for persistent storage. Manage your recipes, pantry inventory, meal planning, shopping lists, and recipe collections all in one place.

![Version](https://img.shields.io/badge/version-2.0.0-blue)
![React](https://img.shields.io/badge/React-18.2.0-61dafb)
![License](https://img.shields.io/badge/license-MIT-green)

## 🎯 Features

### Core Features

- **Recipe Management**: Create, edit, delete, and organize recipes with detailed information
- **Smart Recipe Search**: Filter recipes by course, dietary type, tags, cook time, and favorites
- **Pantry Tracking**: Track ingredients with quantities, units, expiration dates, and categories
- **Meal Planning**: Calendar-based weekly meal planner with drag-and-drop functionality
- **Shopping List**: Auto-generate shopping lists from recipes and meal plans
- **Recipe Collections**: Organize recipes into custom folders/collections
- **Dark Mode**: Full dark mode support with system preference detection

### Advanced Features/

#### 🔥 Cooking Mode (v1.2.0)

- Full-screen step-by-step recipe view
- Large text for easy reading while cooking
- Tap-anywhere navigation
- Keyboard shortcuts (Arrow keys, Space)
- Automatic timer detection from instructions
- Progress tracking

#### 🛒 Smart Shopping Features (v1.3.0)

- **Quick Add Missing Ingredients**: One-click add missing ingredients to shopping list
- **Ingredient Grouping**: Automatic grouping by recipe
- **Common Ingredients Detection**: Consolidates items appearing in multiple recipes
- **Unit Conversion**: Toggle between Imperial and Metric units
- **Copy to Clipboard**: Export shopping list as text

#### 🥗 Recipe Suggestions (v1.1.0)

- Pantry-aware recipe ranking
- Shows recipes you can make now
- Displays ingredient match percentage
- Lists missing ingredients
- Prioritizes favorites and high-match recipes

#### 🔄 Ingredient Substitutions (v1.4.0)

- 50+ ingredient substitution mappings
- Context-aware suggestions
- Shows substitutes for missing ingredients
- Helps when you're missing key ingredients

#### 📁 Recipe Collections (v1.5.0)

- Create custom collections/folders
- Add multiple recipes to collections
- Rename and delete collections
- Filter recipes by collection
- Add existing recipes to collections from collection view
- Visual collection banner with recipe count

#### 📄 Print & Export (v1.4.0)

- Clean print layout for recipes
- PDF generation
- JSON export for backup
- Formatted shopping lists

#### ⏱️ Timer Integration (v1.2.0)

- Automatic timer detection from recipe instructions
- Multiple simultaneous timers
- Start, pause, reset functionality
- Visual timer tray
- Audio notifications when timers complete

### Data Persistence

- **IndexedDB**: Primary storage with full CRUD operations
- **localStorage**: Backup storage for reliability
- **Auto-save**: All changes saved automatically
- **Verification**: Data integrity checks after save operations

## 📋 Version History

### Version 2.0.0 (January 31, 2026)

**Major Release - Collection Enhancements & Bug Fixes**

- ✨ Added "Add Recipes" button to collection view
- ✨ New AddRecipesToCollectionModal with multi-select and search
- 🐛 Fixed Add Missing Ingredients functionality
- 🐛 Fixed normalizeIngredient returning empty strings
- 🐛 Added proper normalizedText to shopping list items
- 🐛 Fixed shopping list display issues with missing ingredients
- 🐛 Improved ingredient parsing fallbacks
- 🔄 Enhanced collection banner UI with exit button
- 🔄 Added recipe name and ID to shopping list items
- 🔄 Improved active collection state tracking

### Version 1.5.0 (January 2026)

**Recipe Collections Release**

- ✨ Create and manage recipe collections/folders
- ✨ Add recipes to multiple collections
- ✨ Filter recipes by collection
- ✨ Collection banner showing active collection
- ✨ Rename and delete collections
- 🔄 Upgraded IndexedDB to version 2 with collections store

### Version 1.4.0 (January 2026)

**Substitutions & Export Release**

- ✨ Ingredient substitutions database (50+ mappings)
- ✨ Substitution suggestions modal
- ✨ Print-friendly recipe layouts
- ✨ PDF generation support
- ✨ JSON export for recipes
- 🔄 Enhanced recipe details modal with new actions

### Version 1.3.0 (January 2026)

**Shopping List Enhancements**

- ✨ Quick Add Missing Ingredients feature
- ✨ Ingredient grouping by recipe
- ✨ Common ingredients consolidation
- ✨ Unit system toggle (Imperial/Metric)
- ✨ Copy shopping list to clipboard
- 🔄 Improved shopping list UI

### Version 1.2.0 (January 2026)

**Cooking Mode & Timers**

- ✨ Full-screen cooking mode
- ✨ Automatic timer detection
- ✨ Multiple timer support
- ✨ Timer notifications
- 🔄 Step-by-step navigation
- 🔄 Keyboard shortcuts

### Version 1.1.0 (January 2026)

**Recipe Suggestions**

- ✨ Pantry-aware recipe ranking
- ✨ Recipe match percentage calculation
- ✨ Missing ingredients display
- ✨ Recipe suggestions modal
- 🔄 computeRecipeMatch algorithm

### Version 1.0.0 (January 2026)

**Initial Release**

- ✨ Recipe CRUD operations
- ✨ Pantry management
- ✨ Meal planning
- ✨ Shopping list
- ✨ IndexedDB persistence
- ✨ Responsive design
- ✨ Dark mode
- ✨ Recipe filtering and search

## 🛠️ Technologies Used

- **React 18.2.0**: Component-based UI framework
- **IndexedDB**: Browser-based database for persistent storage
- **Tailwind CSS**: Utility-first CSS framework
- **Font Awesome**: Icon library
- **JavaScript (ES6+)**: Modern JavaScript features

## 🗂️ Data Structure

### IndexedDB Stores

1. **recipes**: Recipe data with ingredients, instructions, and metadata
2. **pantry**: Pantry inventory with quantities and expiration dates
3. **meal_plan**: Weekly meal planning data
4. **shopping_list**: Shopping list items grouped by recipe
5. **collections**: Recipe collections/folders (v2)

### Recipe Schema

```javascript
{
  id: string,
  name: string,
  description: string,
  ingredients: string[],
  instructions: string[],
  prepTime: number,
  cookTime: number,
  additionalTime: number,
  servings: number,
  type: string,
  course: string,
  dietaryType: string[],
  tags: string[],
  image: string,
  isFavorite: boolean,
  createdAt: string
}
```

### Collection Schema

```javascript
{
  id: string,
  name: string,
  recipeIds: string[],
  createdAt: string
}
```

## 🚀 Getting Started

### Installation

1. Clone or download the repository
2. Open `index.html` in a modern web browser (Chrome, Firefox, Safari, Edge)
3. No build process required - runs directly in the browser!

### Browser Requirements

- Modern browser with IndexedDB support
- JavaScript enabled
- Recommended: Chrome 90+, Firefox 88+, Safari 14+, Edge 90+

## 📖 Usage Guide

### Managing Recipes

1. **Add Recipe**: Click "Add Recipe" button in the header
2. **Edit Recipe**: Click on a recipe card, then click the edit button
3. **Delete Recipe**: Click on a recipe, then click delete (confirmation required)
4. **Favorite Recipe**: Click the star icon on any recipe card

### Using Collections

1. **Create Collection**: Click "Collections" in header → Enter name → Create
2. **Add to Collection**: Click recipe → Collection button → Select collection
3. **View Collection**: Click "Collections" → Click on a collection name
4. **Add More Recipes**: While viewing collection → Click "Add Recipes" button
5. **Exit Collection**: Click "Exit Collection" button in the banner

### Cooking Mode

1. Open any recipe
2. Click the "Cook" button
3. Navigate with:
   - Click/tap anywhere to advance
   - Arrow keys or Space bar
   - Previous/Next buttons

### Smart Shopping

1. Open recipe with missing ingredients
2. Click "Add Missing (X)" button
3. Items automatically added to shopping list
4. View in Shopping List tab
5. Toggle unit system as needed

### Meal Planning

1. Click "Meal Plan" in header
2. Select a day
3. Choose a meal time (Breakfast/Lunch/Dinner/Snack)
4. Select a recipe or add custom meal
5. Use "Add Week to Shopping List" for bulk shopping

### Pantry Management

1. Click "Pantry" in header
2. Add items with quantities and units
3. Set expiration dates
4. Mark items as running low
5. Auto-add from checked shopping list items

## 🎨 UI Features

### Filters

- **Course**: Appetizers, Main Course, Side Dish, Dessert, Beverage
- **Type**: Breakfast, Lunch, Dinner, Snack, Dessert
- **Dietary**: Vegetarian, Vegan, Gluten-Free, Dairy-Free, Nut-Free, Keto, Paleo
- **Cook Time**: Quick (≤30 min), Medium (30-60 min), Long (>60 min)
- **Favorites**: Show only favorited recipes
- **Collections**: Filter by custom collections

### Responsive Design

- Mobile-first approach
- Adaptive layouts for tablet and desktop
- Touch-friendly interface
- Optimized for various screen sizes

## 🔧 Key Functions

### Recipe Matching Algorithm

```javascript
computeRecipeMatch(recipe, pantry);
// Returns: { matchedCount, totalIngredients, percentage, canMake, missing }
```

### Ingredient Parsing

```javascript
parseIngredient(ingredient);
// Returns: { quantity, unit, description }
```

### Ingredient Normalization

```javascript
normalizeIngredient(ingredient);
// Returns: normalized ingredient string for matching
```

## 📝 Data Backup

### Export Options

1. **Individual Recipe**: Print → Save as PDF
2. **All Data**: Use browser DevTools → IndexedDB export
3. **Shopping List**: Copy button → Paste to text file

### Import

- Currently supports manual recipe entry
- Future versions may include JSON import

## 🐛 Known Issues

None currently reported. Please report issues with detailed steps to reproduce.

## 🔮 Future Enhancements

- [ ] Recipe import from URLs
- [ ] Image upload for recipes
- [ ] Nutritional information
- [ ] Recipe scaling calculator
- [ ] Grocery store aisle organization
- [ ] Recipe sharing/export
- [ ] Multi-user support
- [ ] Cloud sync
- [ ] Mobile app version

## 🤝 Contributing

This is a personal project, but suggestions and feedback are welcome!

## 📄 License

MIT License - Feel free to use and modify for personal use.

## 🙏 Acknowledgments

- Icons by Font Awesome
- Styling by Tailwind CSS
- Built with React

## 📞 Support

For questions or issues, please create an issue in the repository.

---

**Built with ❤️ for home cooks and recipe enthusiasts**

Last Updated: January 31, 2026
