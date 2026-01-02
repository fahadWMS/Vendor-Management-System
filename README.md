# 🏢 Vendor Management System

A comprehensive web-based vendor management system designed to streamline corporate procurement operations. This system enables organizations to efficiently track vendors, manage contracts, process purchase orders, monitor budgets, and evaluate vendor performance.

![License](https://img.shields.io/badge/license-ISC-blue.svg)
![Node.js](https://img.shields.io/badge/node.js-v14+-green.svg)
![MySQL](https://img.shields.io/badge/mysql-v8.0+-blue.svg)

## 📋 Table of Contents
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Database Setup](#database-setup)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Project Structure](#project-structure)
- [API Endpoints](#api-endpoints)
- [Usage Guide](#usage-guide)
- [Screenshots](#screenshots)
- [Contributing](#contributing)
- [License](#license)

## ✨ Features

### Core Functionality
- **Vendor Management**: Register, view, and manage vendor information including contact details, service categories, and compliance certifications
- **Contract Management**: Track contract terms, expiry dates, and renewal status (Active, Pending Renewal, Expired)
- **Purchase Order Processing**: Create and manage purchase orders with item descriptions, quantities, and cost tracking
- **Budget Management**: Monitor departmental budgets with allocated and spent amounts
- **Performance Analytics**: Evaluate vendor performance metrics and ratings

### Technical Features
- 🔐 Secure user authentication with password hashing (bcrypt)
- 📊 Interactive dashboard with real-time data visualization
- 🎨 Responsive design with Bootstrap framework
- 🌐 RESTful API architecture
- 🔄 Real-time data updates
- 📱 Mobile-friendly interface
- 🎯 Particle.js animated landing page

## 🛠️ Tech Stack

### Backend
- **Node.js**: JavaScript runtime environment
- **Express.js**: Web application framework
- **MySQL**: Relational database management system
- **bcryptjs**: Password hashing library
- **body-parser**: Request body parsing middleware
- **CORS**: Cross-Origin Resource Sharing support

### Frontend
- **HTML5**: Markup language
- **CSS3**: Styling and animations
- **JavaScript**: Client-side scripting
- **Bootstrap**: Responsive UI framework
- **Particles.js**: Particle animation library

## 📦 Prerequisites

Before you begin, ensure you have the following installed:
- [Node.js](https://nodejs.org/) (v14 or higher)
- [npm](https://www.npmjs.com/) (comes with Node.js)
- [MySQL](https://www.mysql.com/) (v8.0 or higher)
- A code editor (e.g., VS Code)

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/fahadWMS/Vendor-Management-System.git
   cd Vendor-Management-System
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

## 🗄️ Database Setup

1. **Start MySQL server**
   ```bash
   mysql -u root -p
   ```

2. **Create and configure database**
   ```sql
   SOURCE database/vendordatabase.sql;
   ```
   
   Or manually execute the SQL commands:
   ```sql
   CREATE DATABASE VendorManagement;
   USE VendorManagement;
   ```

3. **Update database credentials**
   
   Open `server.js` and update the database configuration:
   ```javascript
   const db = mysql.createConnection({
       host: 'localhost',
       user: 'your_mysql_username',
       password: 'your_mysql_password',
       database: 'VendorManagement',
   });
   ```

## ⚙️ Configuration

The application runs on port **3000** by default. To change this, modify the port number in `server.js`:

```javascript
const PORT = 3000; // Change to your desired port
app.listen(PORT, () => {
    console.log(`Server running on http://localhost:${PORT}`);
});
```

## ▶️ Running the Application

1. **Start the server**
   ```bash
   node server.js
   ```

2. **Access the application**
   
   Open your browser and navigate to:
   ```
   http://localhost:3000/landing.html
   ```

3. **Register a new vendor**
   
   Navigate to the registration page and create your first vendor account.

## 📁 Project Structure

```
Vendor-Management-System/
│
├── server.js                    # Main server file with API endpoints
├── package.json                 # Project dependencies and scripts
├── package-lock.json            # Locked versions of dependencies
├── README.md                    # Project documentation
│
├── src/                         # Backend source files
│   ├── db.js                    # Database connection module
│   └── app.js                   # Application logic
│
├── public/                      # Frontend static files
│   ├── landing.html             # Landing page with particle effects
│   ├── register.html            # Vendor registration page
│   ├── dashboard.html           # Main dashboard
│   ├── vendor.html              # Vendor management page
│   ├── contracts.html           # Contract management page
│   ├── purchase_orders.html     # Purchase order management
│   ├── budget.html              # Budget tracking page
│   ├── vendor_performance.html  # Performance analytics
│   │
│   ├── css/                     # Stylesheets
│   │   ├── landing_page.css
│   │   ├── register.css
│   │   ├── dashboard.css
│   │   ├── vendor.css
│   │   ├── contracts.css
│   │   ├── purchase_orders.css
│   │   ├── budget.css
│   │   └── vendor_performance.css
│   │
│   ├── js/                      # Client-side JavaScript
│   │   └── particles.js         # Particle animation library
│   │
│   └── images/                  # Image assets
│       └── Black-Backgrounds-Desktop.jpg
│
├── database/                    # Database scripts
│   └── vendordatabase.sql       # Database schema and structure
│
└── node_modules/                # Dependencies (auto-generated)
```

## 🔌 API Endpoints

### Vendor Management
- `POST /register-vendor` - Register a new vendor
- `GET /vendors` - Retrieve all vendors
- `GET /vendors/:id` - Get specific vendor details
- `PUT /vendors/:id` - Update vendor information
- `DELETE /vendors/:id` - Delete a vendor

### Contract Management
- `POST /contracts` - Create a new contract
- `GET /contracts` - Retrieve all contracts
- `GET /contracts/:id` - Get specific contract details
- `PUT /contracts/:id` - Update contract information
- `DELETE /contracts/:id` - Delete a contract

### Purchase Orders
- `POST /purchase-orders` - Create a new purchase order
- `GET /purchase-orders` - Retrieve all purchase orders
- `GET /purchase-orders/:id` - Get specific purchase order
- `PUT /purchase-orders/:id` - Update purchase order
- `DELETE /purchase-orders/:id` - Delete a purchase order

### Budget Management
- `POST /budgets` - Create a budget entry
- `GET /budgets` - Retrieve all budget entries
- `PUT /budgets/:id` - Update budget information
- `DELETE /budgets/:id` - Delete a budget entry

### Performance Analytics
- `GET /vendor-performance` - Get vendor performance metrics
- `GET /vendor-performance/:vendorId` - Get specific vendor performance

## 📖 Usage Guide

### 1. Vendor Registration
- Navigate to the registration page
- Fill in vendor details (Name, Email, Phone, Service Category, Compliance Certification)
- Create a secure password
- Submit the form to create a vendor account

### 2. Managing Contracts
- Access the Contracts page from the dashboard
- Add new contracts by specifying vendor, terms, and expiry dates
- Monitor contract status (Active, Pending Renewal, Expired)
- Update or delete contracts as needed

### 3. Creating Purchase Orders
- Go to the Purchase Orders page
- Select a vendor and associated contract
- Enter item description, quantity, and total cost
- Submit to create a new purchase order

### 4. Budget Tracking
- Access the Budget page
- Add departmental budgets with allocated amounts
- Track spent amounts against allocations
- Monitor remaining budget in real-time

### 5. Performance Evaluation
- View the Vendor Performance page
- Analyze delivery times, quality ratings, and compliance scores
- Make informed decisions based on vendor metrics

## 📸 Screenshots

### Landing Page
Beautiful animated particle background welcoming users to the system.

### Dashboard
Centralized hub providing quick access to all system modules.

### Vendor Management
Comprehensive vendor information display and management interface.

### Contract Tracking
Easy-to-use contract management with status indicators.

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the ISC License.

## 👤 Author

**fahadWMS**
- GitHub: [@fahadWMS](https://github.com/fahadWMS)

## 📞 Support

If you have any questions or need help with setup, please open an issue in the GitHub repository.

---

**Note**: Remember to change the default database credentials in `server.js` before deploying to production and never commit sensitive credentials to version control. Consider using environment variables for configuration.
