# E-commerce Project
This project is a comprehensive full-stack e-commerce application developed to simulate a modern online retail platform. It marks a significant architectural evolution from my previous vanilla JavaScript implementation, transitioning to a component-based React frontend and a robust Node.js/Express backend with SQL database integration.

## Structure of Repository
```
├── ecommerce-backend
│   ├── backend
│   │   ├── cart.json
│   │   ├── deliveryOptions.json
│   │   ├── orders.json
│   │   └── products.json
│   ├── defaultData
│   │   ├── defaultCart.js
│   │   ├── defaultDeliveryOptions.js
│   │   ├── defaultOrders.js
│   │   └── defaultProducts.js
│   ├── images
│   │   ├── icons
│   │   ├── products
│   │   └── ratings
│   ├── models
│   │   ├── CartItem.js
│   │   ├── DeliveryOption.js
│   │   ├── Order.js
│   │   ├── Product.js
│   │   └── index.js
│   ├── patches
│   │   ├── sql.js-as-sqlite3+0.2.1.patch
│   ├── routes
│   │   ├── cartItems.js
│   │   ├── deliveryOptions.js
│   │   ├── orders.js
│   │   ├── paymentSummary.js
│   │   ├── products.js
│   │   └── reset.js
│   ├── .eslintignore
│   ├── .eslintrc.json
│   ├── .gitignore
│   ├── documentation.md
│   ├── package-lock.json
│   ├── package.json
│   ├── server.js
│   └── zipFiles.js
├── ecommerce-project
│   ├── public
│   │   ├── images
│   │   │   ├── products
│   │   │   └── ratings
│   ├── src
│   │   ├── assets
│   │   │   ├── images
│   │   │   │   ├── icons
│   │   ├── components
│   │   │   ├── Header.css
│   │   │   ├── Header.jsx
│   │   │   └── Header.test.jsx
│   │   ├── pages
│   │   │   ├── checkout
│   │   │   │   ├── CartItemDetails.jsx
│   │   │   │   ├── CheckoutHeader.css
│   │   │   │   ├── CheckoutHeader.jsx
│   │   │   │   ├── CheckoutPage.css
│   │   │   │   ├── CheckoutPage.jsx
│   │   │   │   ├── CheckoutPage.test.jsx
│   │   │   │   ├── DeliveryDate.jsx
│   │   │   │   ├── DeliveryOptions.jsx
│   │   │   │   ├── DeliveryOptions.test.jsx
│   │   │   │   ├── OrderSummary.jsx
│   │   │   │   ├── OrderSummary.test.jsx
│   │   │   │   ├── PaymentSummary.jsx
│   │   │   │   └── PaymentSummary.test.jsx
│   │   │   ├── home
│   │   │   │   ├── HomePage.css
│   │   │   │   ├── HomePage.jsx
│   │   │   │   ├── HomePage.test.jsx
│   │   │   │   ├── Product.jsx
│   │   │   │   ├── Product.test.jsx
│   │   │   │   ├── ProductsGrid.jsx
│   │   │   │   └── ProductsGrid.test.jsx
│   │   │   ├── orders
│   │   │   │   ├── OrderDetailsGrid.jsx
│   │   │   │   ├── OrderHeader.jsx
│   │   │   │   ├── OrdersGrid.jsx
│   │   │   │   ├── OrdersPage.css
│   │   │   │   ├── OrdersPage.jsx
│   │   │   │   └── OrdersPage.test.jsx
│   │   │   ├── NotFoundPage.css
│   │   │   ├── NotFoundPage.jsx
│   │   │   ├── TrackingPage.css
│   │   │   └── TrackingPage.jsx
│   │   ├── utils
│   │   │   ├── money.js
│   │   │   ├── money.test.js
│   │   ├── App.css
│   │   ├── App.jsx
│   │   ├── index.css
│   │   └── main.jsx
│   ├── .gitignore
│   ├── eslint.config.js
│   ├── index.html
│   ├── package-lock.json
│   ├── package.json
│   ├── setupTests.js
│   ├── vite.config.js
│   └── vitest.config.js
└── README.md
```

## Technical Implementation
* **Full-Stack Architecture:** Engineered a decoupled system with a React frontend (SPA) and a custom Node.js/Express backend, communicating via a RESTful API.
* **Component-Based UI:** Utilized React Hooks (useState, useEffect) to manage complex application state, replacing imperative DOM manipulation with declarative, reusable components.
* **Database Integration:** Integrated Sequelize ORM to manage a relational SQL database. Designed schemas for Products, Orders, and CartItems to ensure referential integrity and data persistence (replacing localStorage).
* **Client-Side Routing:** Implemented React Router to enable seamless navigation between the Product Grid, Checkout, and Order History pages without full page reloads.
* **Backend Search Logic:** Moved search functionality to the server-side (/api/products?search=), implementing efficient keyword filtering and reducing the data payload sent to the client.
* **Modern Tooling:** Migrated the build pipeline to Vite for optimized HMR (Hot Module Replacement) and bundling, and utilized Axios for streamlined HTTP networking.
* **Testing Ecosystem:** Transitioned to Vitest and React Testing Library for unit testing, validating component rendering and user interactions in a virtual DOM environment.

## Key Features
* **Persistent Cart:** Cart data is stored in the database, ensuring users see the same items across different sessions or devices.
* **Real-time Inventory:** Products are fetched dynamically from the backend API, allowing for centralized inventory management.
* **Order Processing:** A comprehensive checkout flow that converts Cart Items into persistent Orders, calculating costs, taxes, and estimated delivery dates on the server.
* **Dynamic Routing:** Individual tracking pages for orders are generated dynamically using URL parameters (e.g., /tracking/:orderId).
* **Responsive Layout:** A mobile-first design philosophy using CSS Grid and Flexbox to ensure compatibility across desktop, tablet, and mobile devices.

## How to Run
This project consists of two parts: the Backend server and the Frontend application.

1) **Starting the Backend -** Open the terminal in your IDE and navigate to the backend directory. Next, install the relevant dependencies and then start the backend server using the following code.
```
cd ecommerce-backend
npm install
npm start
```
The server will run on http://localhost:3000 and automatically seed the database.
<br>
<br>

2) **Starting the frontend Application -** Open a new terminal and navigate to the project directory. Then, start the Vite dev server:
```
cd ecommerce-project
npm install
npm run dev
```
The application will be accessible at http://localhost:5173.
