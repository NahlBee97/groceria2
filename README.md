### **Project Summary: Full-Stack Grocery E-Commerce Platform**

**1. Project Overview**
A modern, full-stack grocery e-commerce web application built with a TypeScript-based tech stack. The platform's core differentiator is its location-based service, which automatically detects a user's location and displays products from the nearest registered grocery stores. It features a multi-tiered administration system, allowing store owners to manage their inventory and a super admin to oversee the entire platform.

**2. Technology Stack**
*   **Frontend:** Next.js (with App Router), TypeScript, Tailwind CSS, shadcn/ui components.
*   **Backend:** Express.js with TypeScript.
*   **Database:** PostgreSQL with Prisma ORM for type-safe database interactions.
*   **Key Features:** User location detection, integration with a third-party Payment Gateway.

**3. Core User Flows**

**A. Customer Flow:**
1.  **Landing & Detection:** A user visits the website. The system requests location permission (or uses IP fallback) to determine their approximate location.
2.  **Store & Product Discovery:** The homepage and product listings automatically display items available from grocery stores nearest to the user's detected location.
3.  **Shopping:** The user browses products, adds them to their cart, and proceeds to checkout.
4.  **Checkout & Payment:** The user selects a delivery/pickup time, enters their details, and completes the payment through the integrated payment gateway (e.g., Stripe, Midtrans).
5.  **Order Confirmation & Tracking:** The user receives an order confirmation and can track the order status (e.g., processing, out for delivery).

**B. Store Admin Flow:**
1.  **Authentication:** A store owner logs into a dedicated admin dashboard.
2.  **Dashboard Overview:** The dashboard shows key metrics for their store: today's sales, order volume, low-stock alerts, and revenue charts.
3.  **Inventory Management:** The admin can add new grocery products, edit existing product details (price, description, images), and update stock levels.
4.  **Order Management:** They can view new orders, update order statuses (e.g., confirmed, preparing, shipped), and manage order fulfillment.
5.  **Sales Analysis:** The admin can view reports and analytics filtered by date to understand sales performance.

**C. Super Admin Flow:**
1.  **Authentication:** A super admin logs into a powerful, centralized admin panel.
2.  **Platform Management:** The super admin can:
    *   Add new stores to the platform, including setting their geographic location and operational details.
    *   Edit or deactivate existing stores.
    *   Manage user roles (assign store admins, manage customer accounts).
3.  **Global Dashboard:** They have a high-level overview of the entire platform's health:
    *   Total Gross Merchandise Value (GMV) across all stores.
    *   Platform-wide sales analytics and trends.
    *   Number of active stores, customers, and transactions.
4.  **Oversight:** Ability to view all stores, orders, and transactions for support and auditing purposes.

**4. Key Features**

**A. Core Application Features:**
*   **Automatic Location Detection:** The primary UX feature that tailors the shopping experience by showing relevant, locally available products.
*   **Store & Product Search:** Users can search for specific items or browse stores by name or category.
*   **Shopping Cart:** A persistent cart that holds items before checkout.
*   **Integrated Payment Gateway:** A secure, seamless checkout process supporting multiple payment methods (credit/debit cards, e-wallets, etc.).
*   **Order History & Tracking:** Users can view their past orders and see the real-time status of current ones.

**B. Store Admin Features:**
*   **Sales Monitoring Dashboard:** Visual charts and data for tracking store performance.
*   **Product Catalog Management:** Full CRUD (Create, Read, Update, Delete) operations for products.
*   **Real-time Inventory Management:** Update stock quantities and receive alerts for low-stock items.
*   **Order Management System:** A dedicated view to process incoming customer orders.

**C. Super Admin Features:**
*   **Centralized Store Management:** Interface to onboard and manage all stores on the platform.
*   **Global Analytics Dashboard:** A comprehensive view of total sales, user growth, and other key performance indicators (KPIs) for the entire platform.
*   **User & Role Administration:** Control over all user accounts and their permissions.

**5. High-Level Database Structure (Entities)**
*   **User:** Contains profiles for Customers, Store Admins, and Super Admins (distinguished by a `role` field).
*   **Store:** Includes store details, location data (latitude/longitude for proximity calculations), and its assigned admin.
*   **Product:** Belongs to a Store. Contains product details, price, and stock level.
*   **Order:** Belongs to a User and a Store. Contains order status, total amount, and shipping information.
*   **OrderItem:** Links an Order to a Product and records the quantity and price at the time of purchase.
*   **Payment:** Records transaction details from the payment gateway, linked to an Order.

This summary provides a clear blueprint for development, outlining the user experience, administrative functions, and the underlying technological architecture.
