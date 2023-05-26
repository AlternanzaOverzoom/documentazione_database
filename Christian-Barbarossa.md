

> Author: Christian Savino Barbarossa

# Welcome to first database!
Here there are some instructions to begin to manage **databases**. In this example we show you a car dealer database.



## How to create and use database
	CREATE DATABASE cardealer; 
		Query OK, 1 row affected (0.001 sec) // database created ✔
		MariaDB [(none)]> use cardealer;
		Database changed // now we can use our database ✔
		
## Create owners' table
	CREATE TABLE owners (
	owner_id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
	name VARCHAR(50),
	surname VARCHAR(50),
	age INT );
**How to verify?**

type command: SHOW COLUMNS FROM name_table;
SHOW COLUMNS FROM owners;

| Field    | Type        | Null | Key | Default | Extra          |
|----------|-------------|------|-----|---------|----------------|
| owner_id | int(11)     | NO   | PRI | NULL    | auto_increment |
| name     | varchar(50) | YES  |     | NULL    |                |
| surname  | varchar(50) | YES  |     | NULL    |                |
| age      | int(11)     | YES  |     | NULL    |                |


		
## Create cars' table

Now we can do the same thing with **cars' table**.

	CREATE TABLE cars (
		year INT,
		brand VARCHAR(255),
		model VARCHAR(255),
		color VARCHAR(30),
		num_plate VARCHAR(6),
		chassis_id INT PRIMARY KEY AUTO_INCREMENT,
		price DECIMAL(10,2)
		owner INT,
		FOREIGN KEY (owner) REFERNCES owners(owner_id)
		);
		
| Field      | Type          | Null | Key | Default | Extra          |
|------------|---------------|------|-----|---------|----------------|
|year |int(11)| YES  |     | NULL    |                |
| brand      | varchar(255)  | NO   |     | NULL    |                |
| model      | varchar(255)  | NO   |     | NULL    |                |
| color      | varchar(30)   | YES  |     | NULL    |                |
| num_plate  | varchar(6)    | YES  |     | NULL    |                |
| chassis_id | int(11)       | NO   | PRI | NULL    | auto_increment |
| price      | decimal(10,2) | YES  |     | NULL    |                |
| owner      | int(11)       | YES  | MUL | NULL    |                |





## How to add an item to the table

**For owner's table you have to type his attributes(fields).**

INSERT INTO `owners` (`name`, `surname`, `age`) VALUES ('Pietro','Romagnoli','40');
> example
> you don't need to declare owner_id because it auto increment its value

|owner_id | name| surname |age |
|--|----|-------|--|
|1|  Pietro |Romagnoli | 40 | 
  
**full table example**
|owner_id|Name|Surname|age|
|--|----|-------|---------|
| 1 |Pietro|Romagnoli|40|
| 2 |Gigietto|Fisichetto|18|
| 3 |Marino|Lascuola|20|
| 4 |Carmela |Alicino|60
| 5 |Martina|Beckam|25|

**For cars table you have to type his attributes(fields).**
INSERT INTO `cars` (`year`,`brand`,`model`,`color`,`num_plate`,`chassis_id`,`price`,`owner`) VALUES ('2009','Nissan','350z','white','abcdef','0','35000','3');

> example
> 
| year | brand |model | color|num_plate| chassis_id | price |owner | 
|--|----|-------|---------|-----|---|-------|---------|
| 2009|Nissan |350z | white | abcdef       |    0 |            35000       |         3 | 
>
>


**full table example**
|year|brand|model|color| num_plate | chassis_id |price  |owner  
|--|----|-------|---------|-----|---|----|---|
| 2009 |Nissan|350z|white|BG122SN|1|350000.00|1|
| 2019 |Bmw|M4|black|AC162VK|2|40000.00|2|
| 2023 |Renault|Arkana|red|BL987OK|3|600000.00|3|
| 2007 |Fiat|Panda|grey|PA777ED|4|13000.00|4|
|2015|Honda|Civic|blue|CK686GB|5|19900.00|5|

**How view elements into table(like examples)**

		SELECT * FROM name_table;
		
## Query
The query is the most important and most used construct of the SQL language: this is a function that allows you to query the database in order to obtain the information contained therein by filtering it, according to your needs, with the introduction of special constructs and keywords.

 **query requested**

 - view all owners who are over 20 years old

		
				
		SELECT * FROM owners WHERE age>20;
							


 - view all cars with a year of registration greater than 2010


		SELECT * FROM cars WHERE year>2010
 - view all cars

		SELECT * FROM cars

