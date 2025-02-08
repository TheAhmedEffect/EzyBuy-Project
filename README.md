# EzyBuy - Online Shopping Management System

## Overview
EzyBuy is a comprehensive online shopping management system designed to deliver a seamless shopping experience. 
Users can browse products, add them to a cart, place orders, make payments, and track deliveries. 
The system efficiently manages users, products, orders, payments, and reviews. 
It also supports dynamic ad displays, multiple payment methods, and flexible delivery options.

---

## Database Schema

### Tables

#### **Users**
- **User_Id** *(Primary Key, VARCHAR2)*: Unique identifier for users.
- **Password** *(VARCHAR)*: User password.

#### **Customer**
- **User_Id** *(Primary Key, Foreign Key → Users, VARCHAR2)*: Unique customer identifier.
- **Customer_Name** *(VARCHAR)*: Name of the customer.
- **Customer_Address** *(VARCHAR)*: Address of the customer.
- **Customer_Contact** *(VARCHAR)*: Contact information.
- **Customer_Mail** *(VARCHAR)*: Email address.
- **Order_History** *(CLOB)*: Historical record of orders.

#### **Admin**
- **User_Id** *(Primary Key, Foreign Key → Users, VARCHAR2)*: Unique admin identifier.
- **Admin_Name** *(VARCHAR)*: Name of the admin.
- **Admin_Role** *(VARCHAR)*: Role assigned to the admin.

#### **Product**
- **Product_Id** *(Primary Key, INT)*: Unique product identifier.
- **Product_Name** *(VARCHAR)*: Name of the product.
- **Product_Price** *(DECIMAL)*: Price of the product.
- **Product_Quantity** *(INT)*: Available stock.
- **Manufacturer_Id** *(Foreign Key → Manufacturer, INT)*: Reference to the product's manufacturer.
- **Category_Id** *(Foreign Key → ProductCategory, INT)*: Reference to the product's category.

#### **Manufacturer**
- **Manufacturer_Id** *(Primary Key, INT)*: Unique identifier for manufacturers.
- **Manufacturer_Name** *(VARCHAR)*: Name of the manufacturer.
- **Manufacturer_Address** *(VARCHAR)*: Address of the manufacturer.

#### **ProductCategory**
- **Category_Id** *(Primary Key, INT)*: Unique identifier for categories.
- **Category_Name** *(VARCHAR)*: Name of the category.

#### **ShoppingCart**
- **Cart_Id** *(Primary Key, INT)*: Unique identifier for shopping carts.
- **Cart_Item_Quantity** *(INT)*: Quantity of items in the cart.
- **Product_Id** *(Foreign Key → Product, INT)*: Product reference.
- **User_Id** *(Foreign Key → Users, VARCHAR2)*: User who owns the cart.

#### **Orders**
- **Order_Id** *(Primary Key, INT)*: Unique order identifier.
- **Cart_Id** *(Foreign Key → ShoppingCart, INT)*: Reference to the cart.
- **Order_Date** *(DATE)*: Date when the order was placed.
- **Order_Amount** *(DECIMAL)*: Total amount of the order.

#### **Payment**
- **Payment_Id** *(Primary Key, INT)*: Unique payment identifier.
- **Payment_Date** *(DATE)*: Date of the payment.
- **Payment_Amount** *(DECIMAL)*: Amount paid.
- **Payment_Method** *(VARCHAR)*: Chosen method of payment.
- **Order_Id** *(Foreign Key → Orders, INT)*: Linked order.

#### **TrackingDetail**
- **Tracking_No** *(Primary Key, INT)*: Unique tracking number.
- **Courier_Name** *(VARCHAR)*: Courier handling the order.
- **Order_Id** *(Foreign Key → Orders, INT)*: Associated order.

#### **Review**
- **Review_Id** *(Primary Key, INT)*: Unique review identifier.
- **Rating** *(INT)*: Rating score provided by the user.
- **Comments** *(CLOB)*: User comments.
- **Review_Date** *(DATE)*: Date when the review was submitted.
- **Product_Id** *(Foreign Key → Product, INT)*: Reviewed product.
- **User_Id** *(Foreign Key → Users, VARCHAR2)*: User who submitted the review.

---

### Views
- **Customer_Orders**: Displays orders placed by customers.
- **Top_Selling_Products**: Lists products based on quantity sold.
- **Low_Stock_Products**: Identifies products with stock below 31 units.
- **Revenue_By_Product_Category**: Displays revenue by category.
- **Product_Performance_By_Rating**: Shows average ratings of products.
- **Orders_Without_Payment**: Lists unpaid orders.
- **Pending_Orders**: Displays orders not yet shipped.
- **Payment_History**: Shows payment records.
- **Customer_Details**: Provides detailed customer information.
- **Product_Review**: Displays customer reviews for products.
- **Tracking_Order_Status**: Shows tracking details of orders.
- **Vip_Customers**: Lists customers who have spent over 50,000.
- **Most_Active_Customers**: Displays customers with the highest order counts.

---

## Features

### Ad Display
- **Sequential Ad Display**: Products are showcased sequentially based on category, popularity, and stock. Ads rotate to ensure diverse product visibility.

### Payment Methods
- **Multiple Payment Options**:
  - Credit/Debit Card
  - Mobile Banking
  - Cash on Delivery (COD)
  - Digital Wallets (e.g., SureCash, bKash)

### Delivery Methods
- **Flexible Delivery Options**:
  - Standard Delivery (3-5 business days)
  - Express Delivery (1-2 business days)
  - In-Store Pickup

---

## Usage

### For Customers
1. **Registration/Login**: Create an account or log in.
2. **Browse Products**: Explore categories and check product details.
3. **Shopping Cart**: Add, update, or remove items.
4. **Checkout**: Select payment and delivery methods to place an order.
5. **Order Tracking**: Track orders using provided tracking numbers.
6. **Review Products**: Submit ratings and reviews for purchased products.

### For Admins
1. **Product Management**: Add, update, or remove products.
2. **Order Management**: View and manage orders, update statuses, handle cancellations.
3. **Customer Management**: View and manage customer accounts.
4. **Payment Management**: Oversee payment details and statuses.
5. **Review Management**: Monitor and manage product reviews.

---

## Installation and Setup

### Database Setup
1. Run provided SQL scripts to create the database schema.
2. Insert initial data.
3. Ensure database connectivity is properly configured.

### Application Setup
1. Configure the application server with correct database settings.
2. Deploy the application and install dependencies.

### Running the Application
1. Start the application server.
2. Access the system via the provided URL.
3. Log in using admin credentials to manage the system.

---

## Contributing
Contributions are welcome! To contribute:
1. **Fork** the repository.
2. **Create a new branch** for your feature or fix.
3. **Commit** your changes and push them.
4. **Submit a pull request** with a detailed description of your updates.

---

## License
This project is licensed under the **MIT License**. See the LICENSE file for details.

---

## Contact
For support or inquiries, contact us at **support@ezybuy.com**.

**EzyBuy - Simplifying Online Shopping!**
