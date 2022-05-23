# shop2it: E-commerce Back End

Back-end half of an npm [express](https://www.npmjs.com/package/express) application to expose the project's MySQL database via API endpoints.  The database hosts data for an e-commerce shop such as products and their prices, categories of products, and tags.

## Installation

Clone this repository into a project folder.

### MySQL

Make sure you have MySQL installed.  Here is an [installation guide](https://coding-boot-camp.github.io/full-stack/mysql/mysql-installation-guide).  Using your OS command line (e.g. `run > cmd` on Windows), navigate to the project folder and connect to MySQL using your user and password:

```MySQL
mysql -u <username> -p
```

Once connected, execute the following commands to create the database and tables:

```MySQL
> source db/schema.sql;
```

### npm

Navigate to the project folder using your terminal of choice.  Run `npm install` to install the project's dependencies, notably [mysql2](https://www.npmjs.com/package/mysql2), [inquirer](https://www.npmjs.com/package/inquirer) for command-line print and prompt, and [dotenv](https://www.npmjs.com/package/dotenv) for secure environment variables.

### .env

Rename or copy the `.env.EXAMPLE` file to `.env`.  Access the file and change the values `MYSQL_ROOT_USER` and `MYSQL_ROOT_PW` to your local MySQL username and password.  The default `MYSQL_DB` database name 'ecommerce_db' can be changed if desired.  `MYSQL_ROOT_HOST` is for use with the npm express server.

Then back in your CLI of choice, run `npm run seed` to seed the database with starting data.

## Running the application

### CLI

Run `npm start` in the project directory using the terminal of your choice.  After a moment, the connection is established to the MySQL database.

### API Client

Using [Insomnia](https://insomnia.rest/) or the API client of your choice, access the API at `localhost:3001/api/:call/:id`

#### Available API calls

Get products, categories, and tags.  Response json array of individual objects.  Optionally, include a single id e.g. `/api/products/1` to retrieve a single object.

```
GET '/api/products'
GET '/api/categories'
GET '/api/tags'
```

Create product, category, tag.  POST object information in the json call body.

```
POST `/api/products`
POST `/api/categories`
POST `/api/tags`
```

Update product, category, tag.  PUT object information in the json call body.

```
PUT `/api/products/:id`
PUT `/api/categories/:id`
PUT `/api/tags/:id`
```

Delete product, category, tag.

```
DELETE `/api/products/:id`
DELETE `/api/categories/:id`
DELETE `/api/tags/:id`
```
