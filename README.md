# StoreFront - E-Commerce Application

**StoreFront** is a modern e-commerce application built using web development technologies taught in the **Code with Mosh** course. The app allows users to browse and purchase products, manage their cart, and handle transactions, providing a seamless shopping experience.

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Project Overview

StoreFront is a fully functional e-commerce web application designed to showcase various products, handle user authentication, and support features like adding items to a shopping cart and completing orders. The app is responsive and optimized for both desktop and mobile devices.

## Features

- **Product Listings**: Browse through various categories and products with sorting and filtering options.
- **Product Detail Page**: View detailed information about each product.
- **Shopping Cart**: Add products to your cart, view cart items, update quantities, and remove products.
- **User Authentication**: Sign up, log in, and manage user profiles.
- **Order Management**: Users can view order history, order details, and track orders.
- **Responsive Design**: Mobile-friendly and optimized for all screen sizes.
- **Search**: Easily search for products by name, category, or brand.

## Technologies Used

This project uses the following technologies:

- **Frontend**:
  - HTML, CSS, and JavaScript
  - Bootstrap for responsive layout and styling
  
- **Backend**:
  - Django for server-side logic
  - MySQL for the database to store product, user, and order data
 
### Example

```plantuml
@startuml
class Customer(models.Model):
    MEMBERSHIP_BRONZE = "B"
    MEMBERSHIP_SILVER = "S"
    MEMBERSHIP_GOLD = "G"

    MEMBERSHIP_CHOICES = [
        (MEMBERSHIP_BRONZE, "Bronze"),
        (MEMBERSHIP_SILVER, "Silver"),
        (MEMBERSHIP_GOLD, "Gold"),
    ]

    first_name = models.CharField(max_length=255)
    last_name = models.CharField(max_length=255)
    email = models.EmailField(unique=True)
    phone = models.CharField(max_length=255)
    birth_date = models.DateField(null=True, blank=True)
    membership = models.CharField(max_length=1, choices=MEMBERSHIP_CHOICES, default=MEMBERSHIP_BRONZE)
    
    class Meta:
        db_table = 'store_customers'
        indexes = [
            models.Index(fields=['last_name', 'first_name'])
        ]
@enduml
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

We would like to acknowledge the following technologies and resources that helped in the development of this project:

- **Code with Mosh**: The e-commerce application is built based on lessons from the **Code with Mosh** course on web development, which provided valuable guidance for structuring and implementing the app.

- **MySQL**: For providing a powerful database to store product, user, and order data, enabling scalable and flexible data management.

- **Django REST Framework**: For providing the backend server environment and API framework, enabling smooth handling of requests, user authentication, and database operations.

