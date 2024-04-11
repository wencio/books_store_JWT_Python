### Flask Bookstore Application

This Flask application serves as a simple bookstore with user authentication and authorization using JSON Web Tokens (JWT). It provides endpoints to view books, add new books, and upload book images, with different access levels for users and administrators.

#### Dependencies

- Flask
- Flask-Restful
- Flask-JWT-Extended

#### Usage

1. **Installation**: Install the required dependencies using pip:

    ```
    pip install flask flask-restful flask-jwt-extended
    ```

2. **Running the Application**: Run the Flask application by executing the script:

    ```
    python app.py
    ```

3. **Accessing the Application**: Once the application is running, access it through a web browser at `http://localhost:5000`.

#### Endpoints

- **GET `/login`**: Renders a login page. Users can log in with their credentials.

- **POST `/login`**: Validates user credentials and generates a JWT token upon successful authentication.

- **GET `/logout`**: Logs out the user and invalidates the JWT token.

- **GET `/books`**: Displays a list of available books. Requires authentication.

- **GET `/addbook`**: Renders a page to add a new book. Only accessible to administrators.

- **POST `/addbook`**: Adds a new book to the bookstore. Requires authentication and administrator privileges.

- **GET `/addimage`**: Renders a page to upload an image for a book. Only accessible to administrators.

- **POST `/addimage`**: Uploads an image for a book. Requires authentication and administrator privileges.

#### JWT Authentication

- The application generates JWT tokens upon successful user authentication.
- JWT tokens are stored as cookies in the client's browser for subsequent authenticated requests.
- User roles (admin/reader) are included as claims in the JWT tokens for authorization purposes.

#### Additional Notes

- The application uses a simple in-memory database for storing user credentials and book data.
- Authentication and authorization are enforced using decorator functions (`jwt_required`, `admin_required`) and JWT token validation.

#### File Structure

```
flask-bookstore/
│
├── app.py
├── templates/
│   ├── addBook.html
│   ├── addimage.html
│   ├── books.html
│   └── register.html
│
└── static/
    └── [uploaded images]
```

This README provides an overview of the Flask Bookstore application, its functionalities, and usage instructions. For detailed implementation details, refer to the source code in `app.py` and associated HTML templates.
