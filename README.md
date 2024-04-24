# Generally information about Nosviak4

 Firstly thank you for choosing & using Nosviak4

## Suggested specifications

OS: `Ubuntu 18.04 -> latest`
minimum *RAM*: `2 GB`
Recommended *RAM*: `8 GB`
Minimum *CPU*: `1 Core`
Recommended *CPU*: `4 Cores`

## Installation

Nosviak4 utilizes a MySQL database for storing data for its clients, this means you will have to
install MySQL-server and setup and create your database and a database user for the cnc to access
via.


### MySQL install for **Ubuntu 20.04**

 - As of Nosviak4 v1.4 the cnc will automatically create your database tables so
 - you only need to install, Config & Create the database as Nosviak4 will do the rest.

    1. Install       `sudo apt install mysql-server`
    2. Start         `sudo systemctl start mysql.service`
    3. Configure     `sudo mysql_secure_installation`
    4. Open MySQL    `sudo mysql`
    5. Create DB     `CREATE DATABASE Nos4;`
    6. Open DB       `USE Nos4;`
 
 - We will now attempt to create the database user for the cnc to access and grant privileges
 - to manage, create & delete users.
   
   CREATE USER 'bolo'@'localhost' IDENTIFIED BY 'bolosech';
   GRANT ALL PRIVILEGES ON * . * TO 'bolo'@'localhost';
   FLUSH PRIVILEGES;

 - Now we much set the configuration options for the database which nosviak2 loads
 - from and parses the information for opening the connection with the database
    indication **1** [location](../assets/config.json) 
    ```json
    "database" : {
        "name" : "Nos4",
        "username" : "nosviak4_client",
        "password" : "vKeXAorBwnBQPk3QG83BeB7ncO7WGjWT",
        "host" : "localhost:3306"
    }, 
    ```

 - Congratulations! you have successfully setup nosviak2
 - [LATER] If you get a `sharing detected` error please run 3 to 4 times to allow rebinding
 - and if that doesn't fix it, please report it to FB
