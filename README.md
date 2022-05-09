# P R I M E Property Management

This is an example of a full-stack website for a fictional property management website called P R I M E Property Management.
The website is developed with Java 11.0 for the business logic, a PostgreSQL 14 database persistance layer developed with pgAdmin4, and
a  HTML, CSS and JavaScript UI layer developed with the Vue.js framework.

The website makes use of RESTful API's 

## Step One: Getting started - The Database

In the `/java` folder, there's a `database` folder where you will find the SQL script to generate the application database tables along with some test data.
Before you run the script, you must first create an empty database in PostgreSQL called scrumlords.  Once the database is created, run the database script called `scrumlordsDb.sql` in a new query window.  SQL script will drop any existing tables and data in the `scrumlords` database and re-create it with new initial test data. Be sure to update the database credentials inside the `application.properties` file located in the `java>src>main>resources` folder.

## Step Two: Spin-up the Property Management server
Open the pom.xml file in IntelliJ and run the application.

## Step Three: Run the user interface
Open the vue subdirectory with Visual Studio Code.  Open a terminal window and execute `npm install` to load all current dependencies.  Finally execute `npm run serve` to launch the UI in your local web browser.

## Step Four: Using the application
The website has public pages for viewing available rental properties as well as password protected user-specific content based on a user’s role.  User roles include Landlord, Renter, and Maintenance worker.  Website content is tailored to one of these four roles.  The following user ids can be used to explore the website functionality

Landlord = `Fred Mertz`

Renter = `Tony Stark`

Maintenance worker = `Sam Carpenter`

Passwords for all user ids is set to `password`


