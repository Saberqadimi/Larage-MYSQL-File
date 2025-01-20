# Import Excel Data into Database Table

This guide will help you import data from an Excel file into a database table. Follow the steps below to create the required table and import the data as explained in the related LinkedIn post.

---

## Prerequisites
1. Ensure your Laravel application is set up.
2. Download the sample Excel file from this repository.

---

## Step 1: Create the Database Table
To create the table where the Excel data will be imported, add the following route in your `web.php` file:

```php
Route::get('/create-users-table', function () {
    // Execute the SQL statement to create the 'peoples' table
    DB::statement("\n        CREATE TABLE peoples (\n            id BIGINT UNSIGNED AUTO_INCREMENT PRIMARY KEY, -- Index\n            user_id VARCHAR(255) UNIQUE NOT NULL,          -- User Id\n            first_name VARCHAR(255) NOT NULL,              -- First Name\n            last_name VARCHAR(255) NOT NULL,               -- Last Name\n            sex ENUM('Male', 'Female', 'Other') NOT NULL,  -- Sex\n            email VARCHAR(255) UNIQUE NOT NULL,            -- Email\n            phone VARCHAR(255) NOT NULL,                   -- Phone\n            date_of_birth DATE NOT NULL,                   -- Date of birth\n            job_title VARCHAR(255) NOT NULL,               -- Job Title\n            created_at TIMESTAMP NULL DEFAULT CURRENT_TIMESTAMP,\n            updated_at TIMESTAMP NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP\n        ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;\n    ");

    // Return a success message
    return 'Table users created successfully.';
});
```

Visit the `/create-users-table` route in your browser to execute this code and create the `peoples` table.

---

## Step 2: Import Data
Follow the steps described in the LinkedIn post to:
1. Update the MySQL configuration.
2. Update the PHP configuration.
3. Restart the web server.
4. Run the raw SQL code to import the Excel data into the `peoples` table.

---

## Notes
- The Excel file should follow the column structure defined in the `peoples` table.
- Make sure to skip the first row of the Excel file if it contains column headers.

For more detailed instructions, check the LinkedIn post linked [here](https://linkedin.com).
