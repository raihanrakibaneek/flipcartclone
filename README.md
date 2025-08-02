# Flipkart Clone - E-Commerce Website

A complete Flipkart-like e-commerce website built with Laravel, featuring a modern responsive design, user authentication, shopping cart, checkout system, and admin panel.

## 🚀 Features

### Customer Features
- **Responsive Homepage** with hero banner, categories, and featured products
- **Product Listing** with search, filter, and sort functionality
- **Product Details** with image gallery and related products
- **Shopping Cart** with quantity management and AJAX updates
- **User Authentication** (login/register/profile management)
- **Checkout System** with address and payment integration
- **Order Management** with order history and tracking
- **Responsive Design** optimized for mobile and desktop

### Admin Features
- **Dashboard** with sales analytics and statistics
- **Product Management** (add, edit, delete products)
- **Category Management** (create and manage categories)
- **Order Management** (view and update order status)
- **User Management** (view customer accounts)
- **Image Upload** with automatic storage management

### Technical Features
- **Laravel 10** framework with modern PHP practices
- **Bootstrap 5** for responsive design
- **MySQL Database** with proper relationships
- **Session-based Cart** system
- **File Upload** with storage management
- **Search & Filter** functionality
- **Pagination** for large datasets
- **AJAX** for dynamic interactions
- **Security** with CSRF protection and validation

## 🎨 Design

The website features a Flipkart-inspired design with:
- **Primary Color**: #2874F0 (Flipkart Blue)
- **Secondary Color**: #FF6200 (Flipkart Orange)
- **Modern UI** with hover effects and animations
- **Responsive Layout** that works on all devices
- **Professional Typography** and spacing

## 📁 Project Structure

```
02.08.2025/
├── app/
│   ├── Http/Controllers/
│   │   ├── HomeController.php
│   │   ├── CartController.php
│   │   ├── AuthController.php
│   │   ├── CheckoutController.php
│   │   └── AdminController.php
│   └── Models/
│       ├── User.php
│       ├── Product.php
│       ├── Category.php
│       ├── Order.php
│       └── OrderItem.php
├── database/
│   ├── migrations/
│   │   ├── create_users_table.php
│   │   ├── create_categories_table.php
│   │   ├── create_products_table.php
│   │   ├── create_orders_table.php
│   │   └── create_order_items_table.php
│   └── seeders/
│       ├── DatabaseSeeder.php
│       ├── CategorySeeder.php
│       ├── ProductSeeder.php
│       └── UserSeeder.php
├── resources/views/
│   ├── layouts/
│   │   └── app.blade.php
│   ├── home.blade.php
│   ├── products.blade.php
│   ├── cart.blade.php
│   └── auth/
│       ├── login.blade.php
│       └── register.blade.php
├── public/
│   ├── css/
│   │   └── app.css
│   └── js/
│       └── app.js
├── routes/
│   └── web.php
├── composer.json
├── env.example
└── README.md
```

## 🛠️ Installation & Setup

### Prerequisites
- PHP 8.1 or higher
- Composer
- MySQL 5.7 or higher
- Web server (Apache/Nginx) or PHP built-in server
- XAMPP/WAMP/MAMP (for local development)

### Step 1: Clone/Download Project
```bash
# If using git
git clone <repository-url>
cd 02.08.2025

# Or download and extract the project files
```

### Step 2: Install Dependencies
```bash
composer install
```

### Step 3: Environment Setup
```bash
# Copy environment file
cp env.example .env

# Generate application key
php artisan key:generate
```

### Step 4: Database Configuration
1. Create a MySQL database named `flipkart_clone`
2. Update the `.env` file with your database credentials:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=flipkart_clone
DB_USERNAME=root
DB_PASSWORD=your_password
```

### Step 5: Run Migrations and Seeders
```bash
# Create database tables
php artisan migrate

# Seed the database with sample data
php artisan db:seed
```

### Step 6: Create Storage Link
```bash
# Create symbolic link for file uploads
php artisan storage:link
```

### Step 7: Start Development Server
```bash
# Using PHP built-in server
php artisan serve

# Or configure your web server to point to the public directory
```

## 👥 Default Users

After running the seeders, you'll have these default accounts:

### Admin User
- **Email**: admin@flipkartclone.com
- **Password**: password123

### Sample Customer
- **Email**: john@example.com
- **Password**: password123

## 📊 Sample Data

The seeder creates:
- **6 Categories**: Electronics, Fashion, Home & Living, Books, Sports, Beauty
- **10 Products**: iPhone 15 Pro, Samsung Galaxy S24, MacBook Air M2, Nike Air Max 270, etc.
- **2 Users**: Admin and sample customer

## 🚀 Usage

### Customer Journey
1. **Browse Products**: Visit the homepage to see featured products
2. **Search & Filter**: Use the search bar and filters on the products page
3. **Add to Cart**: Click "Add to Cart" on any product
4. **Manage Cart**: Update quantities or remove items from cart
5. **Checkout**: Login and proceed to checkout
6. **Place Order**: Fill delivery details and complete payment
7. **Track Orders**: View order history in user profile

### Admin Panel
1. **Login**: Use admin credentials to access admin panel
2. **Dashboard**: View sales statistics and recent orders
3. **Manage Products**: Add, edit, or delete products
4. **Manage Orders**: Update order status and view details
5. **Manage Categories**: Create and manage product categories

## 🔧 Configuration

### File Upload
- Product images are stored in `storage/app/public/products/`
- Make sure the storage link is created: `php artisan storage:link`

### Payment Integration
- Currently supports Cash on Delivery (COD)
- Razorpay integration is prepared but needs API keys
- To enable Razorpay, add your API keys to `.env`:
```env
RAZORPAY_KEY=your_razorpay_key
RAZORPAY_SECRET=your_razorpay_secret
```

### Email Configuration
- Update SMTP settings in `.env` for order notifications
- Default uses mailpit for local development

## 🎨 Customization

### Colors
Update CSS variables in `public/css/app.css`:
```css
:root {
    --primary-color: #2874F0;
    --secondary-color: #FF6200;
    /* ... other colors */
}
```

### Styling
- Main styles: `public/css/app.css`
- Bootstrap 5 is included via CDN
- Font Awesome icons are used throughout

### JavaScript
- Main functionality: `public/js/app.js`
- Includes cart management, notifications, and UI interactions

## 🔒 Security Features

- **CSRF Protection** on all forms
- **Input Validation** with Laravel's validation system
- **SQL Injection Protection** with Eloquent ORM
- **XSS Protection** with Blade templating
- **Session Security** with proper configuration

## 📱 Responsive Design

The website is fully responsive and works on:
- **Desktop**: Full feature set with sidebar filters
- **Tablet**: Optimized layout with collapsible menus
- **Mobile**: Touch-friendly interface with mobile navigation

## 🚀 Deployment

### Production Checklist
1. Set `APP_ENV=production` in `.env`
2. Set `APP_DEBUG=false` in `.env`
3. Configure proper database credentials
4. Set up SSL certificate
5. Configure web server (Apache/Nginx)
6. Set up proper file permissions
7. Configure email service
8. Set up backup system

### Web Server Configuration

#### Apache (.htaccess)
```apache
RewriteEngine On
RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^ index.php [L]
```

#### Nginx
```nginx
location / {
    try_files $uri $uri/ /index.php?$query_string;
}
```

## 🐛 Troubleshooting

### Common Issues

1. **500 Error**: Check file permissions and `.env` configuration
2. **Database Connection**: Verify database credentials and MySQL service
3. **Images Not Loading**: Ensure storage link is created
4. **Composer Issues**: Clear cache with `composer clear-cache`

### Debug Mode
For development, set `APP_DEBUG=true` in `.env` to see detailed error messages.

## 📈 Performance Optimization

- **Image Optimization**: Use compressed images for products
- **Caching**: Implement Redis/Memcached for better performance
- **CDN**: Use CDN for static assets in production
- **Database Indexing**: Add indexes for frequently queried columns

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is for educational purposes. Feel free to use and modify as needed.

## 📞 Support

For support or questions:
- Create an issue in the repository
- Contact: support@flipkartclone.com

## 🎯 Future Enhancements

- **Wishlist** functionality
- **Product Reviews** and ratings
- **Advanced Search** with filters
- **Email Notifications** for orders
- **Multi-language** support
- **Mobile App** integration
- **Analytics** dashboard
- **Inventory Management**
- **Discount Coupons**
- **Social Login** (Google, Facebook)

---

**Happy Coding! 🚀** 
