# 🍴 Christoffel’s Cuisine — Menu App

**Christoffel’s Cuisine** is a React Native mobile application built to manage, browse, and add dishes to a dynamic restaurant menu.  
The app combines **React Navigation**, **React Context API**, and **TypeScript** to deliver an elegant and scalable menu management experience.

---

## 🧭 Overview

This project is designed for restaurants, chefs, or developers who want a simple yet powerful way to organize dishes into categories such as **Breakfast**, **Mains**, and **Desserts**.  

It includes:
- A beautiful home screen with an image header and category tabs.  
- A dynamic menu list that groups dishes by course.  
- A detail view for each item.  
- A form to create and add new dishes.  
- Global state management so that items persist across the app.

---

## ✨ Features

### 🍳 Home Screen
- Displays all dishes categorized under Breakfast, Mains, or Desserts.
- Tab navigation filters dishes by course.
- Header image with live counter of selected dishes.
- Add dishes to your menu using the “+” button.

### 📜 Menu List
- Shows all added dishes grouped by course.
- Displays dish name, description, and price.
- Lets you view full details for any dish.

### 🧁 Item Details Screen
- Presents a dish’s name, course, description, and price in a clean layout.
- Includes a button to return to the menu list.

### 🧾 Add Item Screen
- Create a new dish by entering name, description, price, and course.
- Validates user input (e.g., missing fields or invalid price).
- Saves items globally via Context API.
- Displays confirmation alerts after saving.

### 🌍 Global State Management
- The `MenuContext` handles adding, grouping, and counting dishes.
- Accessible from any screen through a custom `useMenu()` hook.


## 🛠️ Tech Stack

| Category | Technology |
|-----------|-------------|
| Framework | React Native |
| Language | TypeScript |
| Navigation | @react-navigation/native, @react-navigation/bottom-tabs |
| State Management | React Context API |
| Styling | React Native StyleSheet |
| UI Enhancements | ImageBackground, TouchableOpacity, ScrollView |
| Alerts & Validation | React Native built-in components |

---

## ⚙️ Installation

### 1. Clone the repository
```bash


2. Install dependencies
npm install
# or
yarn install

3. Run the app
If using Expo:
npx expo start

Or for React Native CLI:

npx react-native run-android
# or
npx react-native run-ios

📂 Project Structure
.
├── App.tsx                       # Entry point — wraps app in MenuProvider & Navigation
├── src/
│   ├── context/
│   │   └── MenuContext.tsx       # Global state: add/get menu items
│   ├── navigation/
│   │   └── RootTabs.tsx          # Bottom tab navigation
│   ├── screens/
│   │   ├── HomeScreen.tsx        # Displays menu items and tabs
│   │   ├── AddItemScreen.tsx     # Form to create new dishes
│   │   ├── ItemDetailsScreen.tsx # Detailed view of selected dish
│   │   └── MenuListScreen.tsx    # Lists all added dishes
│   ├── types/
│   │   └── index.ts              # Type definitions for Course & Item
│   └── assets/                   # Image and icon resources
└── package.json

🧠 App Flow

Home Screen loads a list of predefined menu items.
Users can filter by course or add items to the global menu context.

Add Item Screen allows users to create new dishes using a form.
Input validation ensures all fields are properly filled.

Menu List Screen displays all added dishes organized by course.
Each item can be tapped to open the Item Details Screen.

Item Details Screen shows detailed info and allows users to navigate back.

🧩 Core Components Explained
🔸 MenuContext

A centralized global store that manages menu data.
It provides:

{
  items: MenuItem[];
  addItem: (item: MenuItem) => void;
  getTotalItems: () => number;
  getItemsByCourse: (course: Course) => MenuItem[];
}

🔸 HomeScreen

Displays an image banner with a restaurant title.

Lists all dishes or filters them by course tabs.

Allows quick adding of dishes to the global menu.

🔸 AddItemScreen

Provides a user-friendly form for dish creation.

Handles validation and confirmation alerts.

Uses custom color scheme (#FF4500, #FF7F50, and #FFF5EB) for visual consistency.

🔸 MenuListScreen

Groups dishes dynamically by their course type.

Each course section displays count and styled headers.

🔸 ItemDetailsScreen

Focuses on readability and presentation of individual dish information.

🧃 UI Design Highlights

Color Palette: Warm oranges and cream tones (#FF4500, #FF7F50, #FFF5EB) for a welcoming, food-related feel.

Typography: Bold headings for dish names; smaller text for descriptions.

Rounded Cards: Soft, elevated cards with shadows for modern appearance.

Consistent Layout: Every screen follows a clear visual hierarchy.

🧱 Example Code (Adding Items)
const handleSave = () => {
  if (!name.trim() || !description.trim() || !price.trim()) {
    Alert.alert('Missing Information', 'Please fill in all fields.');
    return;
  }

  addItem({
    name: name.trim(),
    description: description.trim(),
    course,
    price: parseFloat(price).toFixed(0),
  });

  Alert.alert('Success!', `${name} has been added to your menu.`);
};

🧩 Context Integration Example
// App.tsx
<MenuProvider>
  <NavigationContainer>
    <RootNavigator />
  </NavigationContainer>
</MenuProvider>


This ensures all screens can access useMenu() for reading and writing data.

🧭 Navigation Overview

RootTabs.tsx defines the main tab navigation.

Each tab points to a screen (Home, Menu, Add).

Screens navigate using navigation.navigate('ItemDetails', { item }).

💡 Future Improvements

Add persistent local storage with AsyncStorage.

Integrate Firebase or a backend API for data sync.

Include image upload for menu items.

Add authentication (admin/user roles).

Implement search and filter functionality.

Introduce animations for smoother UI transitions.

👤 Author

Themba Phiri
📍 South Africa
💻 React Native Developer & Student
📧 thembaphiri@example.com

🪪 License

This project is licensed under the MIT License
.
You’re free to modify and distribute it, provided that proper credit is given.

💬 Acknowledgments

React Native documentation for development references.

React Navigation for seamless routing.

Unsplash for free background images.

OpenAI ChatGPT for documentation assistance.

“A well-structured app isn’t just about features — it’s about flow, clarity, and good taste.”
— Themba Phiri


---

git clone https://github.com/your-username/christoffels-cuisine.git
cd christoffels-cuisine
