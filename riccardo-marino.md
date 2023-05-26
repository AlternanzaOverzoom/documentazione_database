
# QUERY

## CREATE A NEW DATABASE NAMED "registro_macchine"
`CREATE DATABASE` registro_macchine;

## WORK ON THE DATABASR NAMED  "registro_macchine"
`use` registro_macchine;

## CREATE A NEW TABLE IN THE DATABASE NAMED "Proprietari"
`CREATE TABLE` Proprietari(
    
### PROPRIETARIO_ID IS AN AUTO INCREMENT VALUES, AND IS THE PRIMARY KEY OF THE TABLE
    proprietario_ID int AUTO_INCREMENT PRIMARY KEY,
	nome text NOT NULL,
	cognome text NOT NULL,
	eta int NOT NULL,
	telefono bigint 
);

## CREATE A NEW TABLE IN THE DATABASE NAMED "Automobili"
`CREATE TABLE` Automobili(


### numeroTelaio IS THE PRIMARY KEY OF THE TABLE AND proprietario IS A FOREIGN KEY THAT IS REFERENCES TO THE Proprietario_ID of the "Proprietari" TABLE
	numeroTelaio int PRIMARY KEY,
	proprietario int NOT NULL,
	targa text NOT NULL,
	annoImmatricolazione int NOT NULL,
	marca text NOT NULL,
	FOREIGN KEY (proprietario) REFERENCES Automobili(proprietario_ID)
);


## SHOW ALL OWNERS WITH AN AGE > 20
`SELECT` *
`FROM` Proprietari
`WHERE` eta>20;

## SHOW ALL CARS REGISTERED AFTER 2010
`SELECT` *
`FROM` Automobili
`WHERE` annoImmatricolazione > 2010

## SHOW ALL CARS
`SELECT * FROM` Automobili;

## SHOW ALL PROPRIETARI
`SELECT` * FROM` Proprietari;

## THESE ARE THE STRUCTURES OF THE TABLES 
### AUTOMOBILI
| numeroTelaio | proprietario | targa | annoImmatricolazione | marca |
|--------------|--------------|-------|----------------------|-------|
|     ...      |    ....      | ...   |           ...        |  ...  |
### PROPRIETARI
| proprietario_ID | nome | cognome | eta | telefono |
|-----------------|------|---------|-----|----------|
|       ....      |  ... |   ...   | ... |    ...   |

## EXAMPLE OF A DATABASE STRUCTURE IN PHPMYADMIN
![database](https://www.researchgate.net/publication/330533248/figure/fig2/AS:717720790253568@1548129379937/MySQL-Database-Structure-from-phpMyAdmin-Database-connections-SQL-query-MEDIUMBLOB.ppm)

## ***MARINO RICCARDO***


