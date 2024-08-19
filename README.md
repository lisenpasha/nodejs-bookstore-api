## Project Structure

The project is structured into two main services:
- User Service
- Book Service

Each service runs independently and can be developed and tested separately.

## Getting Started

### Prerequisites

Make sure you have the following installed on your system:
- Node.js
- npm (Node Package Manager)

### Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/lisenpasha/nodejs-bookstore-api.git
   cd bookstore-api
   ```

2. **Install Dependencies**

Install the root dependencies: 
    ```
   npm install
    ```

Then, navigate to each service directory and install dependencies:

    
    cd user-service
    npm install
    cd ../book-service
    npm install
    cd ..
    
### Alternatively, you can update the package.json file in the bookstore-api directory to the following configuration. This will allow you to run npm install once in the root directory, and it will automatically install dependencies for both the Book and User services:

    {
        "name": "bookstore-api",
        "version": "1.0.0",
        "description": "",
        "main": "index.js",
        "scripts": {
            "develop": "concurrently \"cd user-service && npm run develop\" \"cd book-service && npm run develop\"",
            "postinstall": "cd user-service && npm install && cd ../book-service && npm install"
        },
        "devDependencies": {
            "concurrently": "^6.2.1"
        },
        "keywords": [],
        "author": "",
        "license": "ISC"
    }

3. **Running the Services**

You can run both services simultaneously using the concurrently package or run each service individually.

1-Using Concurrently

Run Both Services Simultaneously
    
    npm run develop

In the root directory of the project(bookstore-api),where the package.json with concurrently is located:
  
This command will start both the User Service on port 8081 and the Book Service on port 8082.

2-Running Each Service Individually On Seperated Terminals

1.User Service

    
    cd user-service
    npm run develop

This will start the User Service on port 8081.

2.Book Service

    
    cd book-service
    npm run develop

This will start the Book Service on port 8082.


4. **API Routes**

User Service (http://localhost:8081)

GET /users - Get all users

GET /users/:id - Get a user by ID

POST /users/export -Export user book readings as CSV (on Postman, after the response is loaded, click on "Save response to file" to download the response as a csv file.)

Book Service (http://localhost:8082)

GET /books - Get all books

GET /books/:id -  Get a book by ID

4. **Running Tests**

1-User Service Tests:

    cd user-service
    npm run test

2-Book Service Tests

    cd book-service
    npm run test


**Project Configuration**

The project configuration is managed through package.json files located in the root directory and each service directory.


**Conclusion**

By following the steps outlined in this README, you should be able to set up, run, and test the Bookstore API. The services are modular, making it easy to maintain and extend functionality.
