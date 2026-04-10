# MERN E-Commerce

A full-stack e-commerce application built with the MERN stack (MongoDB, Express.js, React, Node.js). Features a complete shopping experience with product browsing, cart management, wishlists, reviews, and an admin panel for managing products, orders, and categories -- all wrapped in a modern Material UI interface.

---

## Features

- **User Authentication:** Signup, login, logout with JWT-based cookie authentication
- **Password Recovery:** OTP-based password reset via email using Nodemailer
- **Product Catalog:** Browse products with filtering by brand and category, sorting, and pagination
- **Shopping Cart:** Add, update quantity, and remove items with persistent server-side storage
- **Wishlist:** Save favorite products for later
- **Product Reviews:** Submit and view ratings and reviews per product
- **Order Management:** Place orders, track order status, and view order history
- **Address Management:** Save and manage multiple shipping addresses
- **Admin Panel:** Full dashboard for managing products, orders, brands, and categories
- **Responsive Design:** Material UI components with Framer Motion animations
- **Deployment Ready:** Vercel configuration included for backend deployment

## Tech Stack

### Frontend
- **Library:** React 18
- **State Management:** Redux Toolkit with React-Redux
- **UI Framework:** Material UI (MUI) 5 with Emotion styling
- **Routing:** React Router DOM v6
- **Forms:** React Hook Form
- **HTTP Client:** Axios
- **Animations:** Framer Motion
- **Notifications:** React Toastify
- **Lottie Animations:** lottie-react

### Backend
- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** MongoDB with Mongoose ODM
- **Authentication:** JWT (jsonwebtoken) with cookie-parser
- **Password Hashing:** bcryptjs
- **Email:** Nodemailer (OTP-based password reset)
- **Logging:** Morgan
- **Environment:** dotenv

## Project Structure

```
mern-ecommerce-rishi/
|-- backend/
|   |-- index.js                # Express server entry point (port 8000)
|   |-- database/               # MongoDB connection setup
|   |-- controllers/
|   |   |-- Auth.js             # Signup, login, logout, password reset
|   |   |-- Product.js          # CRUD + filtering/sorting/pagination
|   |   |-- Order.js            # Create, fetch, update order status
|   |   |-- Cart.js             # Add, update, remove cart items
|   |   |-- Wishlist.js         # Add/remove wishlist items
|   |   |-- Review.js           # Create/fetch product reviews
|   |   |-- User.js             # User profile operations
|   |   |-- Brand.js            # Brand management
|   |   |-- Category.js         # Category management
|   |   |-- Address.js          # Address CRUD
|   |-- models/
|   |   |-- User.js             # User schema (name, email, password, role)
|   |   |-- Product.js          # Product schema
|   |   |-- Order.js            # Order schema with status tracking
|   |   |-- Cart.js             # Cart schema (user + product ref)
|   |   |-- Wishlist.js         # Wishlist schema
|   |   |-- Review.js           # Review schema (rating, comment)
|   |   |-- Brand.js            # Brand schema
|   |   |-- Category.js         # Category schema
|   |   |-- Address.js          # Address schema
|   |   |-- OTP.js              # OTP schema for password reset
|   |   |-- PasswordResetToken.js  # Reset token schema
|   |-- routes/                 # Express route definitions
|   |-- middleware/             # Auth middleware
|   |-- utils/                  # Utility functions
|   |-- seed/                   # Database seeding scripts
|   |-- vercel.json             # Vercel deployment config
|   |-- package.json
|-- frontend/
|   |-- src/
|   |   |-- App.js              # Root component with route definitions
|   |   |-- index.js            # React entry point with Redux Provider
|   |   |-- app/                # Redux store configuration
|   |   |-- features/
|   |   |   |-- auth/           # Authentication slice and components
|   |   |   |-- products/       # Product listing and detail components
|   |   |   |-- cart/           # Cart slice and components
|   |   |   |-- order/          # Order slice and components
|   |   |   |-- wishlist/       # Wishlist slice and components
|   |   |   |-- review/         # Review slice and components
|   |   |   |-- admin/          # Admin dashboard components
|   |   |   |-- address/        # Address management components
|   |   |   |-- brands/         # Brand-related components
|   |   |   |-- categories/     # Category-related components
|   |   |   |-- checkout/       # Checkout flow components
|   |   |   |-- navigation/     # Navbar components
|   |   |   |-- footer/         # Footer components
|   |   |   |-- user/           # User profile components
|   |   |-- hooks/              # Custom React hooks
|   |   |-- layout/             # Layout wrapper components
|   |   |-- pages/              # Page-level components
|   |   |-- config/             # API base URL and configuration
|   |   |-- constants/          # App-wide constants
|   |   |-- theme/              # MUI theme customization
|   |   |-- assets/             # Static assets and images
|   |-- public/                 # Public HTML and static files
|   |-- package.json
|-- CODE_OF_CONDUCT.md
|-- LICENSE                     # MIT License
```

## Getting Started

### Prerequisites

- Node.js (v16 or higher recommended)
- npm
- MongoDB (local instance or MongoDB Atlas connection string)

### Environment Variables

Create a `.env` file in the `backend/` directory:

```env
MONGO_URI=mongodb://localhost:27017/mern-ecommerce
JWT_SECRET=your_jwt_secret
ORIGIN=http://localhost:3000
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_email_app_password
```

### Installation

**Backend:**

```bash
cd backend
npm install
```

**Frontend:**

```bash
cd frontend
npm install
```

### Seed the Database (Optional)

```bash
cd backend
npm run seed
```

### Run the Application

**Start the backend server (port 8000):**

```bash
cd backend
npm run dev
```

**Start the frontend development server (port 3000):**

```bash
cd frontend
npm start
```

Open **http://localhost:3000** in your browser.

## Usage

### Customer Flow

1. **Register** a new account or **log in** with existing credentials
2. **Browse products** with filters by brand and category
3. **Add items** to your cart or wishlist
4. **Write reviews** on products you have purchased
5. **Manage addresses** for shipping
6. **Checkout** and place an order
7. **Track orders** from your order history

### Admin Flow

1. Log in with an admin account
2. Access the **admin panel** to manage:
   - Products (create, edit, delete, set stock)
   - Orders (view all orders, update order status)
   - Brands and categories (create, manage)

### API Routes

The backend exposes the following route groups at `http://localhost:8000`:

| Prefix        | Description                  |
|---------------|------------------------------|
| `/auth`       | Signup, login, logout, OTP   |
| `/users`      | User profile management      |
| `/products`   | Product CRUD and queries     |
| `/orders`     | Order creation and tracking  |
| `/cart`       | Cart operations              |
| `/brands`     | Brand management             |
| `/categories` | Category management          |
| `/address`    | Address CRUD                 |
| `/reviews`    | Product reviews              |
| `/wishlist`   | Wishlist operations          |

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
