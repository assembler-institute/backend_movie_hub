`#react` `#express` `#typescript` `#postgres` `#prisma` `#cloudinary` `#backend` `#assembler-institute-of-technology` `#master-in-software-engineering`
# MovieHUB 🎬

Welcome to the MovieHub project, an application to keep track of the movies you are watching. This project is designed to help you learn and practice your backend development skills. Throughout the project, you will be adding functionalities and refactoring your code as you learn new concepts.

![homepage_desktop.png](assets%2Fhomepage_desktop.png)

## Table of Contents:
- [📋 Project Description](#-project-description)
- [🗄️ Data Model](#-data-model)
   - [👤 Users](#-users)
   - [🎬 Movies](#-movies)
   - [🏷️ Genres](#-genres)
- [🚀 Phase 1: Backend with Express, TypeScript, and Node.js](#-phase-1-backend-with-express-typescript-and-nodejs)
- [🏗️ Phase 2: MVC Structure and MongoDB with Mongoose](#-phase-2-mvc-structure-and-mongodb-with-mongoose)
- [🔄 Phase 3: Refactoring with Prisma](#-phase-3-refactoring-with-prisma)
- [🔧 Phase 4: Data Model Migration to PostgreSQL and Multi-client Prisma Support](#-phase-4-data-model-migration-to-postgresql-and-multi-client-prisma-support)
   - [🔗 Data Relationships](#-data-relationships)
- [🔐 Phase 5: Auth0 Integration](#-phase-5-auth0-integration)
   - [📝 Steps for Auth0 Integration with the Frontend](#-steps-for-auth0-integration-with-the-frontend)
- [☁️ Phase 6: Cloudinary Integration [EXTRA]](#-phase-6-cloudinary-integration-extra)
- [ℹ️ Support Resources](#support-resources)

Please note that the table of contents has links to each section, which can be helpful for navigation.

## 📄 Project Description

MovieHub is an application that allows you to manage a list of movies. Each movie in the application has a name, a poster, a score, and a genre. You will be able to perform CRUD (Create, Read, Update, Delete) operations on these movies.

The frontend of the application is built with React. In the user interface, you will be able to view all added movies in a list. Each movie will be displayed with its name, poster, score, and genre. There will be an option to add new movies through a modal or a new page, where you can enter the movie's name, upload a poster image, assign a score, and select a genre. You will also have the option to update the data of existing movies or remove them from the list.

Although the frontend of the application is important for user interaction, the main focus of this project is the backend. As you progress through the project, you will learn and apply different backend technologies and concepts, including Node.js, Express, MongoDB, Prisma, PostgreSQL, Auth0, and Cloudinary. You will learn how these technologies work together to support the functionalities of the application and provide a smooth user experience.

This project is an excellent opportunity to learn and practice your backend development skills while building a functional and attractive movie management application. Good luck!

## 🗄 Data Model

In this project, we will mainly work with three collections or entities: `Users`, `Movies`, and `Genres`. Below, the structure of each of these entities is detailed.

### 👤 Users

The `Users` collection stores information about the application users. Each user has the following fields:

- `id`: A unique identifier for the user.
- `name`: The user's name.
- `email`: The user's email address.
- `password`: The user's password, securely stored.
- `movies`: A list of movies that the user has added to their list.

### 🎬 Movies

The `Movies` collection stores information about the movies that users have added to their list. Each movie has the following fields:

- `id`: A unique identifier for the movie.
- `name`: The movie's name.
- `poster_image`: The URL of the movie poster image, stored in Cloudinary.
- `score`: The movie's score, assigned by the user when adding the movie to their list.
- `genre`: The movie's genre, stored as a reference to the corresponding genre document.

### 🏷️ Genres

The `Genres` collection stores the different movie genres that users can select when adding a movie to their list. Each genre has the following fields:

- `id`: A unique identifier for the genre.
- `name`: The genre's name.

These are the basic data models that we will use in this project. As you progress in the project, you may find the need to add more fields or entities to support new functionalities. Remember, the goal is to learn and practice, so feel free to experiment and make changes as needed.

## 🚀 Phase 1: Backend with Express, TypeScript, and Node.js

In this first phase, your goal is to set up a backend server using Express, TypeScript, and Node.js.

### Requirements

- Install Node.js and npm on your local machine.
- Have basic knowledge of JavaScript and TypeScript.

### Steps

1. **Development environment setup**: Create a new folder for your project and initialize a new Node.js project with npm. Install the necessary dependencies for Express and TypeScript.

2. **Express configuration**: Create a new Express server file and configure it to listen on a port of your choice.

3. **TypeScript configuration**: Create a TypeScript configuration file (`tsconfig.json`) and configure it for your project.

4. **Server creation**: Use Express and TypeScript to create a basic server that can handle HTTP requests (GET, POST, PUT, PATCH, DELETE).

5. **Server testing**: Use a tool like Postman to send requests to your server and verify that it is working correctly.


## 🏗️ Phase 2: MVC Structure and MongoDB with Mongoose

In this phase, your goal is to structure your backend using the Model-View-Controller (MVC) design pattern and connect your application to MongoDB using Mongoose.

Before getting started, it's important to understand the data we'll be handling in our application. We will work with three main collections in our MongoDB database:

**Users**: This collection will store the information of the users in our application. Each user will have at least a name, email, and password.

**Movies**: This collection will store movie information. Each movie will have a name, poster_image, a score, and a genre.

**Genres**: This collection will store different movie genres available. Each genre will have a name.

### Requirements

- Familiarity with the MVC design pattern.
- Basic knowledge of MongoDB and Mongoose.

### Steps

1. **MVC Structure**: Organize your application into three main parts: Models, Views, and Controllers. Although we won't directly work with views in backend development, it's essential to maintain the structure for future integrations. Here's a possible folder structure:

    ```
    /MovieHub
      /src
        /config
           config.ts
        /models
            movie.ts
            user.ts
            genre.ts
        /controllers
            movieController.ts
            userController.ts
            genreController.ts
        /routes
            movieRoutes.ts
            userRoutes.ts
            genreRoutes.ts
        server.ts
        index.ts
    ```

2. **Mongoose Installation**: Install Mongoose in your project using npm.

3. **Connecting to MongoDB**: Use Mongoose to connect your application to your MongoDB database. Make sure to handle any connection errors and log a confirmation message to the console when the connection is successful.

4. **Mongoose Models**: Create Mongoose models for movies, users, and genres. These models will define how the data looks in your database.

5. **Controllers**: Create controllers to handle HTTP requests to your application. Each controller should interact with your database using Mongoose models.

6. **Routes**: Define routes for your application. Each route should direct to a specific controller.

7. **Testing the Application**: Use a tool like Postman to send requests to your application and verify that everything is functioning correctly.


## 🔄 Phase 3: Refactoring with Prisma

In this phase, your goal is to refactor your backend to use Prisma instead of Mongoose. Prisma is an open-source object-relational mapper (ORM) that makes it easier to work with databases in Node.js and TypeScript applications.

- 🚨 At this point we are going to leave the work we have done with mongoose in a separate branch, this way we keep that code "saved" and refactor it anyway.

### Requirements

- Familiarity with Prisma.
- Basic knowledge of MongoDB.

### Steps

1. **Prisma Installation**: Install Prisma in your project using npm.

    ```bash
    npm install @prisma/cli --save-dev
    ```

2. **Prisma Configuration**: Configure Prisma for your project. This will include creating a Prisma configuration file (`prisma/.env`) and a Prisma schema file (`prisma/schema.prisma`).

   To initiate Prisma, run the following command:

    ```bash
    npx prisma init
    ```

3. **Datasource Configuration**: In your `prisma/schema.prisma` file, configure the datasource to use MongoDB. Make sure to update the datasource URL with the connection string to your MongoDB database.

   Here's an example of what this configuration might look like:

    ```prisma
    datasource db {
      provider = "mongodb"
      url      = env("DATABASE_URL")
    }
    ```

   In this example, `DATABASE_URL` is an environment variable that contains the connection string to your MongoDB database. You can define this variable in your `.env` file.

4. **Prisma Models**: Create Prisma models for movies, users, and genres in the `prisma/schema.prisma` file. These models will define what your data looks like in your database.

5. **Prisma Client Generation**: Once you've defined your models, you can generate the Prisma client. The Prisma client is a Node.js module that allows you to access your database.
      To generate the Prisma client, run the following command:

    ```bash
    npm install @prisma/client
    ```
   The install command invokes prisma generate for you which reads your Prisma schema and generates a version of Prisma Client that is tailored to your models.

6. **PrismaClient File Creation**: Create a new `prismaClient.ts` file in the `src/db` folder. In this file, import and create a new instance of the Prisma client. This client will be used to interact with your database.

   Here's an example of what this file might look like:

    ```typescript
    import { PrismaClient } from "@prisma/client";

    const prisma = new PrismaClient();

    export default prisma;
    ```

7. **Controller Refactoring**: Refactor your controllers to use Prisma instead of Mongoose. This will involve changing how you interact with your database.

8. **Database Synchronization**: After refactoring your controllers, you need to synchronize your Prisma models with your database. You can do this by running the `db push` command:

    ```bash
    npx prisma db push
    ```

   🚨 Whenever you update your Prisma schema, you will need to run the prisma db push command to create new indexes and regenerate Prisma Client. This command will also create the tables in your database if they don't exist yet.

9. **Application Testing**: Use a tool like Postman to send requests to your application and verify that everything is working correctly.


## 🔧 Phase 4: Data Model Migration to PostgreSQL and Multi-client Prisma Support

In this phase, your goal is to migrate your data model from MongoDB to PostgreSQL and add support for multiple Prisma clients. You will also define the relationships between your data entities.

### Requirements
- Familiarity with Prisma.
- Basic knowledge of PostgreSQL and MongoDB.
- Understanding of one-to-many and many-to-many relationships.

### 🔗 Data Relationships
In your application, you have three main entities: Users, Movies, and Genres. The relationships between these entities are as follows:

- **Users and Movies**: A user can have many movies, which represents a one-to-many relationship. In the context of a relational database like PostgreSQL, this would typically be represented by a foreign key in the Movies table pointing to the Users table.

- **Movies and Genres**: A movie can have many genres, and a genre can be associated with many movies. This represents a many-to-many relationship. In a relational database, this is typically represented by a join table that includes foreign keys pointing to both the Movies and Genres tables.

### ERD Diagram 
   Example of the entity-relationship diagram (ERD) that provides a graphical representation of the tables, columns and interrelationships of the database.
   ![moviehub_relations.png](assets%2Fmoviehub_relations.png)


### Steps

1. **Creation of .prisma files**: Create two .prisma files, one for each database. In each file, define the corresponding models for each datasource. For example, you can have a `mongo.prisma` file for MongoDB and a `postgres.prisma` file for PostgreSQL.

2. **Configuring the client generator**: In each .prisma file, configure the client generator to generate a client in a specific folder. You can do this by adding an `output` field in the `generator` section of your .prisma file. For example:

    ```prisma
    generator client {
      provider = "prisma-client-js"
      output   = "./generated/mongo_client"
    }
    ```

   Do this for both .prisma files, making sure to change the output path (`output`) for each one.

3. **Generation of Prisma clients**: Generate the Prisma clients using the `prisma generate` command, specifying the schema you want to use. For example:

    ```bash
    npx prisma generate --schema=./prisma/mongo.prisma
    npx prisma generate --schema=./prisma/postgres.prisma
    ```

   This will generate two Prisma clients, one for MongoDB and another one for PostgreSQL.

4. **Creating instances of Prisma clients**: In your `prismaClient.ts` file, create a new instance of each Prisma client. Use an environment variable to determine which client to use. For example:

    ```typescript
    import { PrismaClient as MongoClient } from "../../prisma/generated/mongo_client";
    import { PrismaClient as PostgresClient } from "../../prisma/generated/postgres_client";

    const DATA_SOURCE = process.env.DATA_SOURCE;
   
    type ClientType = {
    [key: string]: MongoClient | PostgresClient;
    };

    export const mongoClient = new MongoClient();
    export const postgresClient = new PostgresClient();

    const clients: ClientType = {
      mongo: mongoClient,
      postgres: postgresClient,
    };

    export default clients[DATA_SOURCE as keyof  ClientType];
    ```

5. **Refactoring of controllers**: Refactor your controllers to use the correct instance of the Prisma client, as determined by the `DATA_SOURCE` environment variable.

6. **Database Synchronization and Migration**: After refactoring your controllers, you need to synchronize your Prisma models with your database. You can do this by running the `db push` command:

    ```bash
    npx prisma db push
    ```

   This command updates your database schema to match your Prisma models. It's important to note that `db push` is not recommended for production databases as it can result in data loss. For production databases, consider using Prisma Migrate, which allows you to version control your database schema changes and apply them incrementally.

   To create a migration with Prisma Migrate, run the following commands:

    ```bash
    npx prisma migrate dev --name init
    ```

   This command will create a new migration and apply it to your database.

7. **Multi-client Prisma Support**: Add support for multiple Prisma clients in your application. This will allow you to switch between different databases easily.
8. **Application Testing**: Use a tool like Postman to send requests to your application and verify that everything is working correctly.
## 🔐 Phase 5: Auth0 Integration

In this phase, your goal is to integrate Auth0 into your application, both on the backend and frontend. Auth0 is an authentication and authorization service that allows you to protect your routes and manage users in your application.

### Requirements

- Familiarity with Auth0.
- Basic knowledge of Express middleware.

### Steps

1. **Create an Auth0 Account**: If you don't have one already, create an account on the Auth0 platform.

2. **Create an API on Auth0**: Within the Auth0 platform, create a new API. This API will represent your backend and provide you with the keys you need to configure authentication.

3. **Install the express-oauth2-jwt-bearer library**: Install the `express-oauth2-jwt-bearer` library in your project using npm.

    ```bash
    npm install express-oauth2-jwt-bearer
    ```

4. **Configure API Keys**: Obtain the API keys you created in Auth0 and add them to your `.env` file. These keys will include your client identifier, client secret, and authorization URL.

5. **Create JWT Verification Middleware**: Create a new file `checkJwt.middleware.ts` in your middleware folder. In this file, configure the middleware to use `express-oauth2-jwt-bearer` and your API keys to validate JWT tokens in requests to your backend.

   Here's an example of how this middleware could look:

    ```typescript
    import { auth } from 'express-oauth2-jwt-bearer';

    const checkJwt = auth({
      audience: process.env.AUTH0_AUDIENCE,
      issuer: process.env.AUTH0_ISSUER_URL,
    });

    export default checkJwt;
    ```

6. **Protect Routes**: Use the `checkJwt` middleware to protect the routes in your backend that require authentication. For example:

    ```typescript
    import express from 'express';
    import checkJwt from './middleware/checkJwt.middleware';

    const app = express();

    app.get('/protected', checkJwt, (req, res) => {
      res.send('This route is protected');
    });
    ```




### 📝 Steps for Auth0 Integration with the Frontend
1. **Create an Application on Auth0**: Within the Auth0 platform, create a new Application. This Application will represent your frontend and provide you with the keys you need to configure authentication.

2. **Install Auth0 SDK for React**: Install the Auth0 SDK for React in your project using npm.

    ```bash
    npm install @auth0/auth0-react
    ```

3. **Configure Auth0 in Your React Application**: Configure Auth0 in your React application. This includes creating an Auth0 configuration file and wrapping your application with the Auth0 provider.

   Here's an example of how this configuration could look:

    ```jsx
    import React from 'react';
    import { Auth0Provider } from '@auth0/auth0-react';

    const App = () => {
      return (
        <Auth0Provider
          domain={process.env.REACT_APP_AUTH0_DOMAIN}
          clientId={process.env.REACT_APP_AUTH0_CLIENT_ID}
          authorizationParams={{
            redirect_uri: window.location.origin + "/home",
            audience: process.env.REACT_APP_AUTH0_AUDIENCE,
        }}
        >
          {/* Your components go here */}
        </Auth0Provider>
      );
    };

    export default App;
    ```

4. **Create Login and Logout Components**: Create components to handle login and logout functionalities. You can use the hooks provided by the Auth0 SDK for React to do this.

   Here's an example of how these components could look:

   ```jsx
   import React from 'react';
   import { useAuth0 } from '@auth0/auth0-react';

   const LoginButton = () => {
     const { loginWithRedirect } = useAuth0();

     return <button onClick={() => loginWithRedirect()}>Log in</button>;
   };

   const LogoutButton = () => {
     const { logout } = useAuth0();

     return <button onClick={() => logout({ returnTo: window.location.origin })}>Log out</button>;
   };
   ```

5. **Obtain JWT for Backend Requests**: To make authenticated requests to your backend, you'll need to include the JWT in the headers of your requests. You can obtain this token using the `useAuth0` hook.

   Here's an example of how you could do this:

   ```tsx
   import React, { useEffect } from 'react';
   import { useAuth0 } from '@auth0/auth0-react';

   const MyComponent = () => {
     const { getAccessTokenSilently } = useAuth0();

     useEffect(() => {
       const getAccessToken = async () => {
         const token = await getAccessTokenSilently();
         // Now you can use this token in the headers of your requests
       };

       getAccessToken();
     }, [getAccessTokenSilently]);

     return <div>My component</div>;
   };
   ```
6. **User Data Handling**: To assign movies to each authenticated user, you can use the `useAuth0` hook in your frontend to get the user's data. This data can then be sent to the backend to determine if the user is new or already exists in your database.

   Here's an example of how you can use the `useAuth0` hook to get the user's data:

    ```tsx
    import { useAuth0 } from "@auth0/auth0-react";
    
    function Component() {
      const { user, isAuthenticated, isLoading } = useAuth0();
    
      if (isLoading) {
        return <div>Loading...</div>;
      }
    
      if (isAuthenticated) {
        console.log(user);
        // Send user data to backend
      }
    
      return <div>Hello {user.name}</div>;
    }
    
    ```
   ### Note on User Data Management
   When a user is authenticated with Auth0, you can use the Auth0 hook to get the user's data. This data includes the user's ID, name, and email address, among other details. You can send this data to your backend to check if the user already exists in your database.

   If the user is new, you can create a new user in your database with the data from Auth0. If the user already exists, you can retrieve the user's details from your database. This way, you can associate the authenticated user with their corresponding movies in your application.



## ☁️ Phase 6: Cloudinary Integration [EXTRA]

In this phase, your goal is to integrate Cloudinary into your backend. Cloudinary is a service that allows you to store, transform, and deliver multimedia content, such as images and videos. In the context of your application, you will use it to upload and store movie posters locally.

### Requirements

- Familiarity with Cloudinary.
- Basic knowledge of file handling in Node.js.

### Steps

1. **Create a Cloudinary account**: If you don't have one yet, create an account on the Cloudinary platform.

2. **Install necessary libraries**: Install the `cloudinary`, `express-fileupload`, and `fs-extra` libraries in your project using npm.

    ```bash
    npm install cloudinary express-fileupload fs-extra
    ```

3. **Configure Cloudinary**: Set up Cloudinary in your backend. This will include configuring your Cloudinary credentials. You can obtain these credentials from your Cloudinary account.

   Here's an example of how this configuration might look:

    ```typescript
    import { v2 as cloudinary } from 'cloudinary';
    cloudinary.config({
      cloud_name: process.env.CLOUDINARY_NAME,
      api_key: process.env.CLOUDINARY_API_KEY,
      api_secret: process.env.CLOUDINARY_API_SECRET
    });
    ```

4. **Configure file upload middleware**: Set up `express-fileupload` as middleware in your application. This will allow you to access the uploaded files in the requests to your backend.

    ```ts
    import fileUpload from 'express-fileupload';
      
    app.use(fileUpload({
     useTempFiles: true,
     tempFileDir: "./uploads",
     limits: {fileSize: 10000000}, // 10MB max file(s) size
     abortOnLimit: true // default: false (if true, files will not be uploaded and an error event will be emitted)
    }));
    ```

5. **Create a route for file upload**: Create a route in your backend to handle file uploads. In this route, use `express-fileupload` to access the uploaded file, `cloudinary` to upload the file to Cloudinary, and `fs-extra` to remove the temporary file.

   Here's an example of how this route might look:

    ```ts
    import express from 'express';
    import { v2 as cloudinary } from 'cloudinary';
    import fs from 'fs-extra';

    const router = express.Router();

    router.post('/upload', async (req, res) => {
      try {
        const file = req.files?.file;
        if (!file) {
          return res.status(400).send('No file uploaded');
        }

        const result = await cloudinary.uploader.upload(file.tempFilePath);
        await fs.unlink(file.tempFilePath);

        res.send(result.secure_url);
      } catch (err) {
        console.error(err);
        res.status(500).send('Server error');
      }
    });

    export default router;
    ```

6. **Test the application**: Use a tool like Postman to send requests to your application and verify that everything is working correctly. Make sure to include a file in the requests to the file upload route.


## Support Resources
- [Prisma](https://www.prisma.io/)
- [MongoDB](https://www.mongodb.com/)
- [PostgreSQL](https://www.postgresql.org/)
- [Cloudinary](https://cloudinary.com/)
- [express-fileupload](https://www.npmjs.com/package/express-fileupload)
- [fs-extra](https://www.npmjs.com/package/fs-extra)
- [Node.js](https://nodejs.org/)
- [Express.js](https://expressjs.com/)
- [TypeScript](https://www.typescriptlang.org/)
- [Auth0](https://auth0.com/)
- [express-oauth2-jwt-bearer](https://www.npmjs.com/package/express-oauth2-jwt-bearer)
- [Auth0 React SDK](https://auth0.com/docs/quickstart/spa/react)



Remember, the goal of this project is to learn and practice. Don't hesitate to ask for help if you get stuck, and make sure to understand each step before moving on to the next one. Good luck!



