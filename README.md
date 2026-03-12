# 🧥 Vintage Fashion - E-Commerce Frontend

A modern, highly responsive, and feature-rich frontend for the "Vintage Fashion" e-commerce platform. Built with React and Vite, this application provides a seamless shopping experience for customers and a powerful, analytics-driven dashboard for administrators. 



## ✨ Core Features

### 🛍️ Customer Portal
* **Authentication:** Secure login/signup with OTP verification and Google OAuth integration.
* **Product Discovery:** Advanced product filtering, searching, and sorting with debounced inputs.
* **Shopping Experience:** Persistent Cart and Wishlist management with real-time stock validation and maximum quantity limits.
* **Checkout & Payments:** Seamless checkout process with address management, coupon application (with proportional discount calculation), and secure payment integration (Razorpay, Wallet, COD).
* **User Dashboard:** Comprehensive profile management, order history, downloadable PDF invoices, and a digital wallet interface for managing refunds and referral bonuses.
* **Live Support:** Real-time customer support chat powered by Socket.io.

### 👨‍💻 Admin Dashboard

* **Analytics & Reporting:** Interactive charts (Bar, Pie, Sparklines) using Recharts to visualize revenue, sales trends, and top-performing products/categories. Downloadable PDF and Excel sales reports.
* **Catalog Management:** Complete CRUD operations for Categories, Brands, Products, and Size/Color Variants (including Cloudinary image uploads).
* **Order & Return Processing:** Detailed order tracking, status updates, and a dedicated interface for approving/rejecting user return requests with automated wallet refunds.
* **Marketing Tools:** Create and manage dynamic Coupons and percentage-based Offers tied to specific products or entire categories.
* **User Management:** Monitor user activity, toggle account statuses (ban/unban), and view detailed wallet transaction ledgers.

---

## 🛠️ Tech Stack & Libraries

* **Core Framework:** React 19, Vite (for lightning-fast HMR and optimized builds)
* **Routing:** React Router v7
* **State Management:** Redux Toolkit (Centralized store for `auth`, `admin`, `cart`, and `wishlist` state)
* **Styling & UI:** Tailwind CSS, Radix UI Primitives, Material-UI (MUI), Lucide React (Icons)
* **Data Fetching:** Axios (configured with interceptors for auth headers and error handling)
* **Real-Time Communication:** Socket.io-client
* **Charts & Visualizations:** Recharts
* **Notifications:** Sonner, React Toastify
* **Authentication:** `@react-oauth/google`

---

## 📂 Architecture & Folder Structure

The project follows a highly modular, feature-based architecture separating the Admin interface from the User interface.

```text
adharsh-tvm-vintage-frontend/
├── src/
│   ├── admin/               # Admin-specific pages and layouts
│   │   ├── dashboard/       # Analytics components (Charts, Stat cards)
│   │   ├── layout/          # Admin Sidebar and Navbar
│   │   ├── pages/           # Admin routes (Products, Orders, Offers, etc.)
│   │   └── products/        # Product management modals
│   ├── components/          # Shared global components (OTP Modals, Protected Routes)
│   ├── hooks/               # Custom React hooks (useToast, auth navigations)
│   ├── lib/                 # Utility functions (Tailwind class merging, formatting)
│   ├── redux/               # Global state management
│   │   ├── api/             # Redux-specific API wrappers
│   │   └── slices/          # State slices (authSlice, cartSlice)
│   ├── services/            # API abstraction layer
│   │   └── api/
│   │       ├── adminApis/   # Separated admin endpoints
│   │       └── userApis/    # Separated user endpoints
│   ├── ui/                  # Reusable UI components (Radix/Shadcn inspired)
│   └── users/               # Customer-facing application
│       ├── components/      # Chat modals, buttons
│       ├── layout/          # Storefront Navbar, Footer, Hero sections
│       └── pages/           # Storefront routes (Shop, Cart, Profile, Checkout)
├── tailwind.config.js       # Custom theme, colors, and animations
└── vite.config.js           # Build and proxy configurations
