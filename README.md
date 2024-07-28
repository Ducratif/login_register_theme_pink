# PHP Admin Login and Register System

This project is a fully functional PHP-based login and registration system for administrators. It incorporates robust security measures and features a modern, futuristic theme.

## Features

- **User Registration**: Allows new administrators to register by providing a username, email, and password.
- **User Login**: Allows administrators to log in with their credentials.
- **Secure**: Protects against common web vulnerabilities such as SQL injection and Cross-Site Scripting (XSS).
- **Modern Design**: Features a sleek, cyberpunk-inspired design for a futuristic look.

## Security Measures

1. **SQL Injection Prevention**: Uses prepared statements to ensure that user input is safely handled.
2. **Cross-Site Scripting (XSS) Protection**: Utilizes `htmlspecialchars` to escape user input before outputting it to the browser.
3. **Password Hashing**: Passwords are securely hashed using `password_hash` before being stored in the database.
4. **Session Security**: Regenerates session IDs to prevent session fixation attacks and includes secure session management practices.
5. **Content Security Policy (CSP)**: Enforces a strict CSP to mitigate the risk of XSS attacks.
6. **Additional Security Headers**: Includes headers like `X-Frame-Options`, `X-Content-Type-Options`, and `X-XSS-Protection` to enhance security.

## Screenshots

### Registration Page
![Registration Page](https://raw.githubusercontent.com/Ducratif/login_register_theme_pink/main/Screenshot_2.png)

### Login Page
![Login Page](https://raw.githubusercontent.com/Ducratif/login_register_theme_pink/main/Screenshot_1.png)

## Installation

1. **Clone the repository**:
    ```sh
    git clone https://github.com/ducratif/php-admin-login-register.git
    ```

2. **Navigate to the project directory**:
    ```sh
    cd login_register_theme_pink
    ```

3. **Configure the database**:
    - Create a database named `boutique`.
    - Import the `admins` table structure:
    ```sql
    CREATE TABLE admins (
        id INT AUTO_INCREMENT PRIMARY KEY,
        username VARCHAR(50) NOT NULL UNIQUE,
        password VARCHAR(255) NOT NULL,
        email VARCHAR(100) NOT NULL UNIQUE,
        created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    );
    ```

4. **Update the database configuration** in `config.php` with your database credentials:
    ```php
    // config.php

    define('DB_SERVER', 'localhost');
    define('DB_USERNAME', 'root');
    define('DB_PASSWORD', '');
    define('DB_NAME', 'boutique');

    function getDbConnection() {
        $conn = new mysqli(DB_SERVER, DB_USERNAME, DB_PASSWORD, DB_NAME);
        if ($conn->connect_error) {
            die("Connection failed: " . $conn->connect_error);
        }
        return $conn;
    }
    ```

5. **Run the application**:
    - Place the project files in your web server's root directory (e.g., `htdocs` for XAMPP or `www` for WAMP).
    - Start your web server and navigate to `http://localhost/login_register_theme_pink/register.php` to register a new admin or `http://localhost/login_register_theme_pink/login.php` to log in.

## Usage

- **Register a new admin**: Fill out the registration form and submit.
- **Login as an admin**: Enter your credentials on the login page and submit.

## Contributing

Contributions are welcome! Please submit a pull request or open an issue to discuss any changes.

## License

This project is open-source and available under the [MIT License](LICENSE).
