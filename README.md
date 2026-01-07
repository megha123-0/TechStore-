Project Title: The "TechStore" Inventory Dashboard

1. Objective
Build a comprehensive Single Page Application (SPA) that manages a product inventory. This project assesses your ability to structure web pages (HTML), design responsive layouts (CSS), manage application logic (JavaScript ES6+), and interact with external APIs.
2. The Scenario
You have been hired by a retail startup to build their internal Inventory Management System. The client needs a dashboard where they can:
View current products fetched from a database.
Analyze stock levels and total inventory value.
Add new products via a form.
Persist data so their changes aren't lost on page refresh.
3. API Details (The Backend)
You will use the DummyJSON API to fetch initial data.
API Endpoint: https://dummyjson.com/products
Documentation: https://dummyjson.com/docs/products
Method: GET to fetch data.
4. Technical Requirements
Part A: HTML Structure (The Skeleton)
Semantic Tags: You must use <header>, <nav>, <main>, <section>, and <footer>.
The Table: Display products in a <table> with columns for: Image, Name, Price, Category, Stock, Actions (Delete button).
The Form: Create a form with validation attributes (required, min, type="number") to add new products.
Part B: CSS Styling (The Look)
Layouts:Use Flexbox for the Navigation bar and Form alignment.
Use CSS Grid for the main dashboard layout (Sidebar vs. Main Content) or Product Cards.
Responsiveness: Use @media queries. The layout must switch from a Sidebar view (Desktop) to a stacked column view (Mobile) on screens smaller than 768px.
Visuals: Use CSS Variables (:root) for theme colors. Implement transition effects on buttons (hover states).
Part C: JavaScript Logic (The Brains)
ES6+ Features: Use const/let (no var), Arrow Functions, Destructuring (e.g., const { title, price } = product), and Template Literals.
Fetch API: Use async/await to retrieve data from the Dummy API on page load.
DOM Manipulation: Dynamically render the table rows based on the data array. Do not hardcode HTML rows.
Array Methods: Use .map() to render the list and .reduce() to calculate the Total Inventory Value displayed in the stats header.
Part D: Advanced & "Bonus" Features
Storage: Implement localStorage. When a user adds or deletes a product, save the updated array to the browser. On page reload, check localStorage first before fetching from the API.
Event Delegation: Attach a single event listener to the Table container to handle "Delete" button clicks (utilizing Event Bubbling).
Closures: Encapsulate your main logic (or a specific utility function) inside a closure or module pattern to avoid polluting the global scope.
5. Implementation Guide (Step-by-Step)
If you are stuck, follow this logic flow to complete the assignment.
Step 1: Setup & HTML
Create your index.html. Layout your "Stats Panel" (top), "Input Form" (left or top), and "Product Table" (center).
Step 2: Fetching Data
Write an asynchronous function
Step 3: Rendering (DOM)
Create a function renderTable(data) that clears the current table body (innerHTML = '') and loops through the data.
Tip: Use object destructuring inside your loop for cleaner code.
Step 4: Handling Forms
Select your form and add a submit event listener.
Prevent the default refresh: e.preventDefault().
Create a new product object from the input values.
Add it to your products array.
Important: Call renderTable() again to update the UI immediately.
Step 5: Event Delegation (Deleting)
Instead of adding a listener to every delete button:
Add one listener to the <tbody>.
Check if (e.target.classList.contains('delete-btn')).
Find the ID of the product and remove it from the array.
Re-render the table.

The Expected Output
"When you run your final application, you will see a clean, modern dashboard titled 'TechStore Admin'.
At the very top of the screen, a Stats Bar will greet you, automatically calculating and displaying the total count of items and the total dollar value of your entire inventory. Below this, the main area displays a neatly organized Product Table filled with real data fetched from the live internet (the DummyJSON API).
The application is interactive and responsive. On one side (or at the top on mobile), there is an 'Add Product' Form. When you type a new item's details and hit 'Add', the table updates instantly to include your new product, and the Total Value number at the top recalculates immediately—all without the page ever reloading.
Each row in the table also has a 'Delete' button. Clicking this removes the item instantly. Most importantly, the app remembers your work: if you refresh the page or close the browser window and come back later, your new products and changes will still be there, saved safely in the browser's storage."
