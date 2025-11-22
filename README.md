# Efeedor LMS - Learning Management System

A comprehensive Learning Management System (LMS) built with CodeIgniter PHP framework, designed for creating, managing, and delivering online courses with support for multiple instructors, students, and advanced features.

Live Demo Details
Link : [https://lmsdemo.efeedor.com/] username : demo@efeedor.com password : Demo@123

## 📋 Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Directory Structure](#directory-structure)
- [Payment Gateways](#payment-gateways)
- [Multi-language Support](#multi-language-support)
- [API Documentation](#api-documentation)
- [User Roles](#user-roles)
- [Addons](#addons)
- [Updates](#updates)
- [Support](#support)

## ✨ Features

### Core Features
- **Course Management**: Create and manage courses with multimedia content
- **Video Lessons**: Support for video, audio, document, and text-based lessons
- **User Management**: Multiple user roles (Admin, Instructor, Student)
- **Category Management**: Organize courses by categories
- **Enrollment System**: Students can enroll in courses
- **Progress Tracking**: Track student progress and completion
- **Quiz System**: Create quizzes and assessments
- **Certificate Generation**: Generate certificates upon course completion

### Additional Features
- **Blog System**: Integrated blog for announcements and updates
- **E-Book Management**: Sell and manage e-books
- **Course Bundles**: Package multiple courses together
- **Tutor Booking**: Schedule and manage tutoring sessions
- **Custom Pages**: Create custom pages for your site
- **Social Login**: Login with Facebook and other social platforms
- **JWT Authentication**: Secure API authentication
- **REST API**: Full RESTful API for mobile apps and integrations

### Admin Features
- **Dashboard Analytics**: Comprehensive dashboard with statistics
- **User Management**: Manage all users (admins, instructors, students)
- **Course Approval**: Review and approve instructor-created courses
- **Payment Management**: Track all payment transactions
- **System Settings**: Configure site settings, email, and more
- **Language Management**: Manage multi-language translations
- **Addon Management**: Install and manage addons

## 🔧 Requirements

### Server Requirements
- **PHP**: Version 5.3.7 or higher (PHP 7.4+ recommended)
- **MySQL**: 5.6 or higher / MariaDB 10.0 or higher
- **Web Server**: Apache with mod_rewrite enabled or Nginx
- **Extensions**: 
  - OpenSSL PHP Extension
  - PDO PHP Extension
  - Mbstring PHP Extension
  - Tokenizer PHP Extension
  - XML PHP Extension
  - GD Library (for image processing)
  - cURL PHP Extension

### Recommended
- PHP 7.4+ for better performance
- MySQL 5.7+ or MariaDB 10.2+
- Apache with mod_rewrite
- SSL Certificate (HTTPS) for production

## 🚀 Installation

### Step 1: Download and Extract
1. Download the LMS package
2. Extract files to your web server directory (e.g., `public_html`, `www`, or `htdocs`)

### Step 2: Database Setup
1. Create a new MySQL database for the LMS
2. Note down your database credentials:
   - Database host (usually `localhost`)
   - Database name
   - Database username
   - Database password

### Step 3: Configure Database
1. Open `application/config/database.php`
2. Update the database configuration:
```php
$db['default'] = array(
    'hostname' => 'localhost',
    'username' => 'your_username',
    'password' => 'your_password',
    'database' => 'your_database_name',
    'dbdriver' => 'mysqli',
    // ... other settings
);
```

### Step 4: Install via Web Interface
1. Navigate to your domain in a web browser
2. You will be redirected to the installation page
3. Follow the installation wizard:
   - Fill in database credentials
   - Create admin account
   - Complete the installation

### Step 5: Set Permissions
Make sure these directories are writable:
- `application/cache/`
- `application/logs/`
- `uploads/`
- `assets/` (if applicable)

```bash
chmod -R 755 uploads/
chmod -R 755 application/cache/
chmod -R 755 application/logs/
```

### Step 6: Configure Base URL
1. Open `application/config/config.php`
2. The base URL is auto-detected, but you can set it manually if needed

## ⚙️ Configuration

### Environment Configuration
The application environment can be set in `index.php`:
```php
define('ENVIRONMENT', isset($_SERVER['CI_ENV']) ? $_SERVER['CI_ENV'] : 'production');
```

Options: `development`, `testing`, `production`

### Email Configuration
Configure email settings in Admin Panel → Settings → System Settings → Email Settings

### Payment Gateway Configuration
Configure payment gateways in Admin Panel → Settings → Payment Settings

### Timezone Configuration
Set timezone in Admin Panel → Settings → System Settings

## 📁 Directory Structure

```
lmsdemo/
├── application/           # Application code
│   ├── cache/            # Cache files
│   ├── config/           # Configuration files
│   ├── controllers/      # MVC Controllers
│   ├── core/             # Core extensions
│   ├── helpers/          # Helper functions
│   ├── hooks/            # Hooks
│   ├── language/         # Language files
│   ├── libraries/        # Custom libraries and third-party
│   ├── models/           # MVC Models
│   ├── views/            # View templates
│   │   ├── backend/      # Admin panel views
│   │   ├── frontend/     # Frontend views
│   │   ├── install/      # Installation views
│   │   └── lessons/      # Lesson views
│   └── logs/             # Log files
├── assets/               # Static assets (CSS, JS, images)
│   ├── backend/          # Admin panel assets
│   ├── frontend/         # Frontend assets
│   └── global/           # Shared assets
├── languages/            # Multi-language JSON files
├── system/               # CodeIgniter core files
├── themes/               # Custom themes
├── uploads/              # User uploaded files
├── update_pack/          # Update packages
├── backups/              # Backup files
├── composer.json         # Composer dependencies
└── index.php             # Entry point
```

## 💳 Payment Gateways

The LMS supports multiple payment gateways:

- **Stripe**
- **Razorpay**
- **PayPal**
- **Paystack**
- **Flutterwave**
- **Cashfree**
- **Xendit**
- **PayU**
- **SSLCommerz**
- **AamarPay**
- **bKash**
- **Doku**
- **PagSeguro**
- **Skrill**
- **Tazapay**
- **MaxiCash**
- **Offline Payment**

Configure payment gateways in Admin Panel → Settings → Payment Settings

## 🌍 Multi-language Support

The LMS supports 16 languages:

- English
- Arabic
- Chinese
- French
- Georgian
- German
- Hindi
- Indonesian
- Italian
- Khmer
- Portuguese
- Romanian
- Russian
- Spanish
- Turkish
- Urdu

Language files are located in the `languages/` directory. Users can switch languages from the frontend.

## 📱 API Documentation

The LMS includes a RESTful API for:
- Mobile applications
- Third-party integrations
- Instructor API
- File management API

API endpoints are located in:
- `application/controllers/Api.php` - Main API controller
- `application/controllers/Api_instructor.php` - Instructor API
- `application/controllers/Api_files.php` - File management API

API uses JWT (JSON Web Token) for authentication.

## 👥 User Roles

### Admin
- Full system access
- Manage all users, courses, and settings
- View analytics and reports
- Configure payment gateways and system settings

### Instructor
- Create and manage courses
- Upload course content (videos, documents, etc.)
- Manage enrolled students
- View course analytics
- Create quizzes and assessments

### Student
- Browse and enroll in courses
- Access enrolled courses
- View progress and certificates
- Purchase courses
- Interact with course content

## 🔌 Addons

The LMS supports various addons:
- Certificate Generator
- Course Bundles
- E-Book Management
- Tutor Booking
- And more...

Addons are located in `application/controllers/addons/` and can be managed from the Admin Panel.

## 🔄 Updates

To update the LMS:

1. **Backup your installation** (database and files)
2. Go to Admin Panel → Settings → System Settings → Update Product
3. Upload the update file from `update_pack/` directory
4. Click "Update"
5. Clear browser cache (Ctrl+Shift+R / Cmd+Shift+R)

**Current Version**: v6.7

## 📝 Default Routes

- `/login` - Login page
- `/sign_up` - Registration page
- `/home` - Home/Dashboard
- `/admin` - Admin dashboard
- `/instructor` - Instructor dashboard
- `/api` - API endpoints

Custom routes can be configured in `application/config/routes.php`

## 🔒 Security

- Keep PHP and MySQL updated
- Use HTTPS in production
- Set proper file permissions
- Regularly backup database and files
- Keep the LMS updated to the latest version
- Use strong passwords for admin accounts

## 📞 Support

For support and documentation:
- Check the admin panel documentation
- Review error logs in `application/logs/`
- Contact your developer or support team

## 📄 License

This is a commercial Learning Management System. Please refer to your license agreement for usage terms.

## 🛠️ Troubleshooting

### Common Issues

**500 Internal Server Error**
- Check file permissions
- Review error logs in `application/logs/`
- Verify PHP version compatibility

**Database Connection Error**
- Verify database credentials in `application/config/database.php`
- Ensure MySQL service is running
- Check database user permissions

**File Upload Issues**
- Check `uploads/` directory permissions
- Verify PHP upload limits in `php.ini`
- Check available disk space

**Page Not Found (404)**
- Ensure mod_rewrite is enabled (Apache)
- Verify `.htaccess` file exists
- Check base URL configuration

## 📚 Additional Resources

- [CodeIgniter Documentation](https://codeigniter.com/user_guide/)
- PHP Documentation
- MySQL Documentation

---

**Note**: Always keep backups before making any changes or updates to your installation.

