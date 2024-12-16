# Go Game Todo Server

The **Go Game Todo Server** is a backend application designed for managing the core logic and API services for a to-do app. Despite the name, it is not a game server but a robust backend for organizing tasks and to-do lists. It is built with modern TypeScript tooling and libraries, offering scalability, security, and performance.

### [Go Game Client (React Native)](https://github.com/Mhp23/go-game-client/)

## Features

- **Authentication**: Secure user authentication using JSON Web Tokens (JWT) and bcrypt for password hashing.

- **Validation**: Strong runtime validation with `zod` and OpenAPI integration for generating API documentation.

- **Security**: Enhanced security with `helmet` and `express-rate-limit`.

- **Task Scheduling**: Support for scheduled tasks using `node-cron`.

- **Logging**: High-performance logging with `pino` and `pino-pretty` for structured logs.

- **Database**: MongoDB integration using `mongoose`.

## Tech Stack

### Core Libraries

- **[express](https://expressjs.com/)**: A minimal and flexible Node.js web application framework.
- **[mongoose](https://mongoosejs.com/)**: MongoDB object modeling for Node.js.
- **[bcrypt](https://github.com/kelektiv/node.bcrypt.js)**: For hashing passwords securely.
- **[jsonwebtoken](https://github.com/auth0/node-jsonwebtoken)**: JWT-based authentication.
- **[zod](https://github.com/colinhacks/zod)**: TypeScript-first schema validation.
- **[swagger-ui-express](https://github.com/scottie1984/swagger-ui-express)**: For serving auto-generated API documentation.
- **[node-cron](https://github.com/kelektiv/node-cron)**: Task scheduling.
- **[helmet](https://github.com/helmetjs/helmet)**: Secure HTTP headers.
- **[express-rate-limit](https://github.com/nfriedly/express-rate-limit)**: Rate limiting middleware for Express.
- **[pino](https://getpino.io/#/)**: Fast and lightweight logging.

### Development Tools

- **[TypeScript](https://www.typescriptlang.org/)**: For a strongly-typed development experience.
- **[tsup](https://tsup.egoist.dev/)**: A simple and fast bundler for TypeScript.
- **[tsx](https://github.com/esbuild-kit/tsx)**: TypeScript execution and REPL.
- **[biome](https://biomejs.dev/)**: All-in-one linter and formatter.
- **[vitest](https://vitest.dev/)**: A fast unit testing framework.
- **[husky](https://typicode.github.io/husky/)**: Git hooks for pre-commit validations.
- **[lint-staged](https://github.com/okonet/lint-staged)**: Run linters on staged files.

## Getting Started

### Prerequisites

- **Node.js**: Ensure you have Node.js installed (v18+ recommended).
- **MongoDB**: A running MongoDB instance.

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/mhp23/go-game-server.git
   cd go-game-server
   ```

2. Install dependencies:

   Using **pnpm**:

   ```bash
   pnpm install
   ```

   Alternatively, for **npm** or **yarn** (If you're using a different package manager, you should change the Husky pre-commit commands based on that):

   ```bash
   npm install
   # or
   yarn install
   ```

3. Set up environment variables:

   Create a `.env` file in the root of the project and configure it like the following template:

   ```env
   # Environment Configuration
   NODE_ENV="development"
   PORT=8080
   HOST="localhost"

   # CORS Settings
   CORS_ORIGIN="http://localhost:*"

   # Rate Limiting
   SENSITIVE_RATE_LIMIT_WINDOW_MS="25"
   COMMON_RATE_LIMIT_WINDOW_MS="1000"
   COMMON_RATE_LIMIT_MAX_REQUESTS="100"

   # Databases
   MONGO_CONNECTION_URI="mongodb://localhost:27017/Go_Game_DB"

   # Password
   SALT_ROUNDS=10

   # JWT
   JWT_ACCESS_SECRET="YOUR_ACCESS_SECRET"
   JWT_REFRESH_SECRET="YOUR_REFRESH_SECRET"
   JWT_ACCESS_EXPIRY="15m"
   JWT_REFRESH_EXPIRY="7d"
   ```

4. Run the application:

   - **Development Mode**:
     ```bash
     pnpm dev
     ```
   - **Production Mode**:
     ```bash
     pnpm start
     ```

### Scripts

- **`dev`**: Start the server in development mode with hot-reloading and pretty logs.
- **`build`**: Build the project for production.
- **`start`**: Build and start the server in production.
- **`clean`**: Clean up the `dist` and `coverage` directories.
- **`lint`**: Run the linter.
- **`lint:fix`**: Fix linting issues.
- **`format`**: Format the codebase.
- **`test`**: Run all unit tests.

## Folder Structure

```
├── dist               # Compiled output (generated by tsup)
├── src
    ├── __tests__      # Unit and integration tests
│   ├── api-docs       # API documentation generation
│   ├── controllers    # Route handlers
│   ├── core           # Main configurations (e.g., DB connection)
│   ├── middlewares    # Express middlewares
│   ├── models         # Mongoose models
│   ├── routes         # Express route definitions
│   ├── schemas        # Zod definitions and validators
│   ├── services       # Business logic
│   ├── utils          # Utility functions
│   └── index.ts       # Entry point
└── .env               # Environment variables
```

## API Documentation

The application uses `swagger-ui-express` to serve API documentation. To access the docs, run the server and navigate to:

```
http://localhost:<PORT>
```

## Contributing

1. Fork the repository.
2. Create a new branch for your feature/bug fix.
3. Commit your changes.
4. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

