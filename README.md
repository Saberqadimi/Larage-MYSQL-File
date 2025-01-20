# Import Large Excel Data into Database Table
### Import 1 million data into a database with Excel in under 10 seconds

This repository provides a straightforward way to import data from an Excel file into a MySQL database table named `peoples`. Follow the steps below to create the table and import your data.

## Table Creation

To create the `peoples` table, you can use the following route in your Laravel project:

```php
Route::get('/create-users-table', function () {
    // Execute the SQL statement to create the 'peoples' table
    DB::statement("
        CREATE TABLE peoples (
            id BIGINT UNSIGNED AUTO_INCREMENT PRIMARY KEY, -- Index
            user_id VARCHAR(255) NOT NULL,                -- User Id
            first_name VARCHAR(255) NOT NULL,             -- First Name
            last_name VARCHAR(255) NOT NULL,              -- Last Name
            sex ENUM('Male', 'Female', 'Other') NOT NULL, -- Sex
            email VARCHAR(255) NOT NULL,                  -- Email
            phone VARCHAR(255) NOT NULL,                  -- Phone
            date_of_birth DATE NOT NULL,                  -- Date of birth
            job_title VARCHAR(255) NOT NULL,              -- Job Title
            created_at TIMESTAMP NULL DEFAULT CURRENT_TIMESTAMP,
            updated_at TIMESTAMP NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
        ) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
    ");

    // Return a success message
    return 'Table users created successfully.';
});
```

## Steps to Import Data

1. **Download the Excel File:**
   Download the sample Excel file provided in this repository.

2. **Create the Table:**
   Visit the route `/create-users-table` in your browser or execute it via a tool like Postman to create the `peoples` table in your database.

3. **Follow the LinkedIn Guide:**
   For more detailed instructions, check the LinkedIn post linked [here](https://www.linkedin.com/feed/update/urn:li:ugcPost:7287050711148720128/).

## Notes

- Ensure that your database connection settings in Laravel are correctly configured in the `.env` file.
- If you encounter any issues during the import process, check your server logs for debugging.



