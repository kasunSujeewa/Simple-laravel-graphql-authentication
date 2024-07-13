
# Simple Laravel GraphQL Authentication

A simple implementation of GraphQL authentication using Laravel. This repository provides a basic structure to get started with user authentication in a Laravel application using GraphQL.

## Features

- User registration
- User login
- Authentication via GraphQL
- Middleware for protected routes
- JWT (JSON Web Token) for token-based authentication

## Requirements

- PHP >= 8.1
- Composer
- Laravel = 11.x
- Node.js & npm (for frontend scaffolding if needed)

## Installation

1. **Clone the repository:**

    ```bash
    git clone https://github.com/kasunSujeewa/Simple-laravel-graphql-authentication.git
    cd Simple-laravel-graphql-authentication
    ```

2. **Install dependencies:**

    ```bash
    composer install
    npm install
    ```

3. **Setup environment:**

    Copy the `.env.example` to `.env` and update the necessary environment variables such as database configuration.

    ```bash
    cp .env.example .env
    ```

4. **Generate application key:**

    ```bash
    php artisan key:generate
    ```

5. **Run migrations:**

    ```bash
    php artisan migrate
    ```

6. **Start the development server:**

    ```bash
    php artisan serve
    ```

## Usage

1. **Register a new user:**

    Use a GraphQL client like [GraphiQL](https://github.com/graphql/graphiql) or [Insomnia](https://insomnia.rest/) to send a mutation request.

    ```graphql
    mutation {
      register(name: "Test User", email: "test@example.com", password: "password") {
        token
        user {
          id
          name
          email
        }
      }
    }
    ```

2. **Login a user:**

    ```graphql
    mutation {
      login(email: "test@example.com", password: "password") {
        token
        user {
          id
          name
          email
        }
      }
    }
    ```

3. **Access protected routes:**

    Add the `Authorization` header with the `Bearer` token received from the login or register mutation.

    ```graphql
    query {
      user {
        id
        name
        email
      }
    }
    ```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
