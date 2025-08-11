# How to Setup Backend - Node.js (Express.js) with TypeScript and Prisma using PostgreSQL, MySQL or MongoDB

Learn more about the following technologies:
- [Postgres SQL](https://www.postgresql.org/docs/current/)
- [Node.js](https://nodejs.org/docs/latest/api/)
- [Express.js](https://expressjs.com/)
- [Prisma ORM](https://www.prisma.io/docs/orm)

## Get Started:

### Step 1. Create a Folder for your Project:
- Name it whatever you want, for ex. `nodejs-expressjs-postgresql`.

Organizing your project into a dedicated folder ensures all related files and configurations are in one place, making it easier to manage.


### Step 2. Initialize NPM
- Open your terminal and type `npm init -y` to initialize the package.json file:
```console
npm init -y
```
Running npm init -y generates a package.json file, which serves as the project's metadata file. It lists your dependencies, scripts, and other project configurations.

The package.json file is essential for managing the dependencies and scripts required to build and run your project.


### Step 3. Install Dependencies
This installs the core dependencies required for your project to function. Here’s what each dependency does:
  
- **express**: A web framework for building RESTful APIs.
- **cors**: Middleware for handling Cross-Origin Resource Sharing.
- **dotenv**: For loading environment variables from .env files.
- **bcryptjs**: Library for hashing passwords.
- **zod**: A schema validation library for TypeScript.
- **jsonwebtoken**: For creating and verifying JSON Web Tokens (JWTs).
- **crypto-js**: For encryption and decryption.
- **swagger-ui-express & swagger-jsdoc**: Tools for API documentation.
- **nodemailer**: For sending emails.
- **ejs**: A templating engine for HTML rendering.
- **@prisma/client**: The Prisma ORM client for database interactions.

These libraries provide the functionality needed for tasks like database interactions, user authentication, and API documentation.

```console
npm install express cors dotenv bcryptjs zod jsonwebtoken crypto-js swagger-ui-express swagger-jsdoc nodemailer ejs date-fns @prisma/client
```


### Step 4. Install Development Dependencies
```console
npm install typescript ts-node @types/node @types/express @types/cors @types/bcryptjs @types/jsonwebtoken @types/crypto-js @types/nodemailer @types/ejs @types/date-fns @types/swagger-ui-express @types/swagger-jsdoc prisma --save-dev
```
Development dependencies are tools and types that assist in development but are not required in production. This includes TypeScript-related tools and type definitions for installed libraries.

TypeScript improves code quality by enforcing static typing. The type definitions (e.g., @types/node) allow you to use TypeScript effectively with Node.js and other libraries.


### Step 5. Initialize TypeScript
```console
npx tsc --init
```
The npx tsc --init command generates a tsconfig.json file, which configures the TypeScript compiler.

This step sets up TypeScript in your project and allows you to customize settings like target JavaScript version, module resolution, and more.


### Step 6. Initialize Prisma with Data Source Provider. 
You can choose between PostgreSQL, MySQL, and MongoDB:
```console
npx prisma init --datasource-provider postgresql
```
or
```console
npx prisma init --datasource-provider mysql
```
or
```console
npx prisma init --datasource-provider mongodb
```
The npx prisma init command creates a Prisma configuration file (prisma/schema.prisma) and a .env file for database connection settings.

Prisma uses this schema file to map your database structure and interact with it programmatically.


### Step 7. Prisma Migration
```console
npx prisma migrate dev --name init
```
After initializing your Prisma Schema Migration, you can now create your database schema and then,
```console
npx prisma migrate dev
```
- npx prisma migrate dev --name init: Initialize migration name.
- npx prisma migrate dev: Creates and applies database migrations based on your Prisma schema.

Migrations ensure your database schema is up-to-date and synchronized with your application code.



### Step 8. Prisma Studio
```console
npx prisma studio
```
The npx prisma studio command launches a web-based GUI to view and interact with your database.

This tool makes it easier to inspect and manage database records during development.
