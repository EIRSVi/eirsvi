================================================================================
APPSOURCE SCHOOL MANAGEMENT SYSTEM - PROJECT STRUCTURE AND DESCRIPTION
================================================================================

Project Repository: shiliaiwei/Appsource-School-Management-System
Language Composition: PHP (70.9%), JavaScript (18.1%), CSS (10.9%), Other (0.1%)
Technology Stack: Pure PHP (No PHP Framework Used), MySQL Database

================================================================================
PROJECT OVERVIEW
================================================================================

Appsource School Management System (SMS) is a comprehensive, clean, and modern 
school management solution designed to automate all aspects of school operations. 
Built entirely in Pure PHP without any frameworks, it provides a complete suite 
of applications covering student information systems, grading, billing, library 
management, and internal communications.

The system is designed for educational institutions of all sizes and provides 
role-based access control with different permission levels for various staff 
members including Super Users/Administrators, Head Masters, Directors of Studies, 
Teachers, Secretaries, Librarians, and other staff members.

================================================================================
KEY FEATURES
================================================================================

1. ACADEMIC MANAGEMENT
   - Admissions Management
   - Student Information System
   - Examination Management
   - Custom Exam-set Configuration
   - Report Cards Generation
   - Class Marksheets
   - Subject Marksheets

2. USER AND STAFF MANAGEMENT
   - Employee/Teacher Management
   - Role-based Permission System
   - User Access Control with Multiple Roles

3. FINANCIAL MANAGEMENT
   - Student Billing System
   - Finance Reports
   - Ledger Book Management
   - Payment Processing

4. LIBRARY MANAGEMENT
   - Complete Library System
   - Book Cataloging and Tracking

5. CLASS MANAGEMENT
   - Class Organization
   - Class-level Reports and Analytics

6. COMMUNICATION
   - Built-in Messaging System
   - Announcements and Notifications

7. REPORTING AND ANALYTICS
   - Advanced Reports
   - Dashboard Analytics
   - Financial Reports
   - Academic Performance Tracking

8. ADDITIONAL FEATURES
   - Contact Management
   - School Settings and Configuration
   - Mobile App Support

================================================================================
DIRECTORY STRUCTURE
================================================================================

root/
├── README.md                    - Main project documentation
├── LICENSE                      - MIT License file
├── index.html                   - Landing/Index page
├── util.php                     - Utility functions (non-DB operations)
│
├── core/                        - Core configuration and initialization
│   └── init.php                - Database and application initialization
│                                 Loads configuration, database settings,
│                                 school settings from database
│
├── classes/                     - PHP Classes for core functionality
│   ├── DB.php                  - Database connection and query handler
│   ├── Encryption.php          - Encryption/Decryption utilities
│   ├── Hash.php                - Password hashing functions
│   ├── Input.php               - User input handling and validation
│   ├── Redirect.php            - Page redirection utilities
│   ├── Session.php             - Session management
│   ├── Token.php               - CSRF token generation and validation
│   └── Validate.php            - Input validation methods
│
├── functions/                   - Utility and helper functions
│   └── functions.php           - Application-wide helper functions
│                                 - Password generation
│                                 - Date formatting
│                                 - Currency formatting
│                                 - HTML escaping
│
├── pages/                       - Page templates and views
│   ├── dashboard.php           - Main dashboard interface
│   ├── announcements/          - Announcement pages
│   ├── library/                - Library management pages
│   ├── payments/               - Payment processing pages
│   ├── school_setup/           - School configuration pages
│   └── users/                  - User management pages
│
├── includes/                    - Common include files
│   ├── nav_header.php          - Header/Top navigation
│   ├── nav_footer.php          - Footer navigation
│   └── nav_side_bar.php        - Sidebar navigation
│
├── css/                         - Stylesheets
│   └── (CSS files for styling)
│
├── js/                          - JavaScript files
│   └── (JavaScript functionality)
│
├── images/                      - Image assets
├── img/                         - Additional image resources
├── fonts/                       - Font files
├── font-awesome/                - Font Awesome icon library
│
└── nbproject/                   - NetBeans project configuration

================================================================================
CORE COMPONENTS DESCRIPTION
================================================================================

1. DATABASE LAYER (classes/DB.php)
   - Handles all database connections
   - Provides query execution methods
   - Returns query results as objects
   - Singleton pattern for single database instance

2. SECURITY COMPONENTS
   
   a) Encryption.php
      - Handles data encryption/decryption
      - Ensures sensitive data protection
      
   b) Hash.php
      - Password hashing for user authentication
      - Uses secure hashing algorithms
      
   c) Token.php
      - CSRF (Cross-Site Request Forgery) protection
      - Session token validation
      
   d) Validate.php
      - Input validation and sanitization
      - Form data validation

3. SESSION MANAGEMENT (classes/Session.php)
   - User session handling
   - Session persistence
   - Session data storage and retrieval

4. INPUT HANDLING (classes/Input.php)
   - Retrieves and processes user input
   - GET/POST parameter handling
   - Input sanitization

5. NAVIGATION COMPONENTS (includes/)
   - nav_header.php: Top navigation bar with user menu
   - nav_footer.php: Footer information
   - nav_side_bar.php: Main application menu with role-based visibility

================================================================================
CONFIGURATION
================================================================================

Database Configuration (core/init.php):
   - Host: 127.0.0.1 (localhost)
   - Username: root
   - Password: (blank - configured per installation)
   - Database: appsource-ss-5

Remember Token Configuration:
   - Cookie Name: 'hash'
   - Cookie Expiry: 604800 seconds (7 days)

Session Configuration:
   - Session Name: 'user'
   - Token Name: 'token'

School Settings (Retrieved from m_setting table):
   - School Name
   - School Motto
   - School Logo Path
   - School Address
   - School Telephone
   - School Email
   - School Location

================================================================================
USER ROLES AND ACCESS LEVELS
================================================================================

1. SUPER USER/ADMINISTRATOR
   - Full system access
   - All configuration and management capabilities
   - Access to all modules
   - User: super | Password: super

2. DIRECTOR OF STUDIES
   - Academic management
   - Examination and grading
   - Report generation
   - User: appsource-dos | Password: appsource-dos

3. HEAD MASTER
   - School-wide administration
   - User management
   - General reports
   - User: appsource-hm | Password: appsource-hm

4. LIBRARIAN
   - Library management
   - Book cataloging
   - Library reports
   - User: appsource-lib | Password: appsource-lib

5. TEACHER
   - Class management
   - Student grading
   - Report access
   - User: appsource-teacher-1 | Password: appsource-teacher-1

6. ADDITIONAL ROLES
   - Deputy Head Master
   - Secretary
   - Bursar

================================================================================
KEY TECHNOLOGIES
================================================================================

Backend:
   - PHP 5.4.0 or later
   - Pure PHP (No frameworks)
   - Object-Oriented Programming
   - Autoloader for automatic class loading

Database:
   - MySQL
   - Centralized data storage
   - Role-based data access

Frontend:
   - HTML5
   - CSS3
   - JavaScript
   - Font Awesome Icons

Server Requirements:
   - Web server capable of executing PHP (Apache, Nginx, etc.)
   - MySQL database server
   - PHP 5.4.0 or later
   - Full database permissions

================================================================================
INSTALLATION AND SETUP
================================================================================

1. Upload the Appsource SMS files to your web server directory

2. Create a new MySQL database
   Example: CREATE DATABASE appsource-sms;

3. Import the database schema using the provided database file

4. Configure database connection in core/init.php:
   Edit the $GLOBALS['config'] array with your database details:
   - 'host': Your MySQL server address
   - 'username': Your database user
   - 'password': Your database password
   - 'db': Your database name

5. System is ready to use
   Access the application through your web browser

================================================================================
UTILITY FUNCTIONS (util.php and functions/functions.php)
================================================================================

Utility Functions:

1. getAlevelGrade($arrayOfGradeWeights, $type_id)
   - Calculates A-level grades from component grades
   - Supports both principal and subsidiary subjects
   - Converts numeric grades to letter grades

2. showError($error)
   - Displays error messages to users
   - Includes contact information for support

3. generatePassword($length = 8)
   - Creates random secure passwords
   - Excludes ambiguous characters
   - Used for initial user account creation

4. escape($string)
   - Converts special characters to HTML entities
   - Prevents XSS attacks

5. english_date($date)
   - Formats dates in English format (j M Y)
   - Example: 24 May 2026

6. english_date_time($date)
   - Formats dates and times in English (jS F Y l:a)
   - Example: 24th May 2026 Sunday:am

7. redirect($message, $url)
   - Displays message and redirects user
   - JavaScript-based redirection

8. ugandan_shillings($value)
   - Formats numbers as Ugandan currency
   - Adds "UGx" suffix with comma separators

9. addMonthsToDate($months, $dateCovert)
   - Adds months to a given date
   - Returns formatted date string

================================================================================
APPLICATION FLOW
================================================================================

1. INITIALIZATION
   - index.html serves as entry point
   - Redirects to login or dashboard based on session

2. AUTOLOADING
   - core/init.php registers SPL autoloader
   - Classes from classes/ directory loaded automatically
   - functions/functions.php included for utility functions

3. CONFIGURATION LOADING
   - Database configuration read from core/init.php
   - School settings retrieved from m_setting table
   - Global variables set (SCHOOL_NAME, MOTTO, LOGO_PATH, etc.)

4. NAVIGATION
   - nav_header.php included for top navigation
   - nav_side_bar.php provides main menu
   - Role-based menu items displayed based on user permissions

5. PAGE RENDERING
   - Pages from pages/ directory rendered
   - Includes applied for navigation and layout
   - CSS and JavaScript loaded from respective directories

================================================================================
DATABASE TABLES
================================================================================

Key Tables:
   - m_setting: School configuration and settings
   - users: User accounts with role assignments
   - students: Student information
   - classes: Class definitions
   - subjects: Subject information
   - exams: Examination records
   - grades: Student grades and marks
   - payments: Student payment records
   - books: Library book catalog
   - announcements: System announcements
   - messages: Internal messaging system

================================================================================
SECURITY FEATURES
================================================================================

1. Password Security
   - Hashing using Hash class
   - Secure password generation

2. Input Protection
   - Input validation and sanitization
   - HTML entity escaping
   - SQL injection prevention through prepared queries

3. Session Security
   - Session token management
   - CSRF token validation
   - Remember-me functionality with secure cookies

4. Access Control
   - Role-based permission system
   - Session-based authentication
   - User role verification for page access

================================================================================
SUPPORT AND CONTACT
================================================================================

For technical support and inquiries:
   WhatsApp: +256-705-656565
   Email: info@appsourcetechnologies.com

For complete system with database:
   Visit: https://appsourcetechnologies.com/buy

================================================================================
LICENSE
================================================================================

Appsource School Management System is released under the MIT License.
This is Free Software.

================================================================================
PROJECT STATISTICS
================================================================================

Repository: shiliaiwei/Appsource-School-Management-System
Repository ID: 1248417938
Language Breakdown:
   - PHP: 70.9%
   - JavaScript: 18.1%
   - CSS: 10.9%
   - Other: 0.1%

Total Components:
   - 7 Core Classes
   - Multiple utility functions
   - 6+ page modules
   - 3 navigation includes
   - Comprehensive styling and scripting

================================================================================
NOTES
================================================================================

- No external PHP frameworks used; built on pure PHP
- Suitable for educational institutions of all sizes
- Mobile app support available
- Fully customizable for institutional needs
- Designed for ease of use by both technical and non-technical staff
- Comprehensive role-based access control system
- Scalable architecture supporting growing institutions

================================================================================
END OF DOCUMENTATION
================================================================================
