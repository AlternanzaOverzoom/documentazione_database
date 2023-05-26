
# Database RegistroAuto

## Table Proprietari
	CREATE TABLE Proprietari(
	    ID int NOT NULL auto_increment, 
	    Nome varchar(255) NOT NULL,
	    Cognome varchar(255) NOT NULL,
	    Indirizzo varchar(255) NOT NULL,
	    Sesso varchar(1) NOT NULL,
	    Eta int(3) NOT NULL,
	    PRIMARY KEY (ID)
	);
	
**Come viene creata una riga della tabella:**	

	INSERT INTO Proprietari (Nome, Cognome, Indirizzo, Sesso, Eta)
	VALUES ("Sophia", "Santomauro", "Via Catullo 148", "F", 17); 

|ID|Nome|Cognome|Indirizzo|Sesso|Eta|
|--|----|-------|---------|-----|---|
| 1 |Sophia|Santomauro|Via Catullo 148|F|17|
| 2 |Beatrice|Larosa|Via Catullo 148|F|50|
| 3 |Giuseppe|Losito|Via Bisceglie 18|M|19|
| 4 |Francesco|Bruno|Via Laspecchia 40|M|45|
| 5 |Margherita|Asselti|Via Montone 33|F|14|

## Table Cars
	CREATE TABLE Cars(
	    Ntelaio int NOT NULL auto_increment , 
	    Modello varchar(255) NOT NULL,
	    Colore varchar(255) NOT NULL,
	    AnnoMatricolazione int NOT NULL,
	    Prezzo int NOT NULL,
	    Targa varchar(7) NOT NULL,
	    IDProp int NOT NULL,
	    PRIMARY KEY (Ntelaio),
	    FOREIGN KEY (IDProp) REFERENCES Proprietari (ID)
	);
	
**Come viene creata una riga della tabella:**	

	INSERT INTO Cars  (Modello, Colore, AnnoMatricolazione, Prezzo, Targa, IDProp)
	VALUES ("Mercedes", "Grigio", 2017, 22120, "EW902DZ",1);
	
|Ntelaio|Modello|Colore|AnnoMatricolazione|Prezzo|Targa|IDProp|
|---------|----------|-------|------------------------|--------|------|--|
| 5 |Mercedes|Grigio|2017|22120|EW902DZ|1|
| 7 |Audi|Arancione|2000|23500|BU386KW|2|
| 8 |Ferrari|Rosso|2020|499000|FV486WP|3|
| 9 |Panda|Bianco|1999|14850|ER929NG|4|
| 10 |Jeep|Nero|2015|26900|AB123CD|5|

**Query per vedere i proprietari che hanno età maggiore di 20:**
	
	SELECT * FROM Proprietari WHERE Eta>20;
	
**Query per vedere quali macchine hanno anno di matricolazione dopo il 2010:**
	
	SELECT * FROM Cars WHERE AnnoMatricolazione >2010;
