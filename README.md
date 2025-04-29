# Backend Perpus - Library Management System API

A RESTful API for managing a library system built with Express.js, Sequelize ORM, and MySQL.

## 📚 Description

This project is a backend application for managing a library system. It provides APIs for user authentication, book management, borrowing operations, and user management. The system is designed to help libraries track their book inventory and user borrowing history efficiently.

## 🛠️ Technologies Used

- **Node.js** - JavaScript runtime environment
- **Express.js** - Web application framework
- **Sequelize** - ORM for database interactions
- **MySQL** - Relational database
- **JWT** - Authentication and authorization
- **Bcrypt** - Password hashing
- **Multer** - File uploading middleware

## 🔧 Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/hadi-rch/backend-perpus.git
   cd backend-perpus/final-project
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up your environment variables:
   ```
   Create a .env file with the following variables:
   DB_USERNAME=your_db_username
   DB_PASSWORD=your_db_password
   DB_NAME=your_db_name
   DB_HOST=localhost
   JWT_SECRET=your_jwt_secret
   ```

4. Initialize the database:
   ```bash
   npx sequelize-cli db:create
   npx sequelize-cli db:migrate
   npx sequelize-cli db:seed:all   # Optional for development data
   ```

5. Start the server:
   ```bash
   npm start
   ```

## 📊 Database Schema

The application uses the following main models:

- **Users** - Stores user information
- **Books** - Contains book records with title, author, and other details
- **Borrowings** - Manages book borrowing records
- **Categories** - Classification of books

## 🔐 Authentication

The API uses JWT (JSON Web Token) for authentication. To access protected routes, include the JWT token in the Authorization header:

```
Authorization: Bearer <your_token>
```

## 🚀 API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login and get token

### Books
- `GET /api/books` - Get all books
- `GET /api/books/:id` - Get a specific book
- `POST /api/books` - Add a new book (Admin only)
- `PUT /api/books/:id` - Update a book (Admin only)
- `DELETE /api/books/:id` - Delete a book (Admin only)

### Borrowings
- `GET /api/borrowings` - Get borrowing history
- `POST /api/borrowings` - Borrow a book
- `PUT /api/borrowings/:id` - Return a book

### Users
- `GET /api/users` - Get all users (Admin only)
- `GET /api/users/:id` - Get user details
- `PUT /api/users/:id` - Update user details
- `DELETE /api/users/:id` - Delete a user (Admin only)

### Categories
- `GET /api/categories` - Get all categories
- `POST /api/categories` - Add a new category (Admin only)
- `PUT /api/categories/:id` - Update a category (Admin only)
- `DELETE /api/categories/:id` - Delete a category (Admin only)

## 👥 User Roles

The system supports two types of users:
- **Regular Users** - Can browse books, borrow/return books, and manage their profile
- **Administrators** - Have access to all features, including user management and book inventory control

## 🧪 Testing

Run the test suite with:
```bash
npm test
```

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💻 Author

- **Hadi** - [GitHub Profile](https://github.com/hadi-rch)

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request
