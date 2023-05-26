# Database Concessionaria
## Creazione Database
`CREATE DATABASE concessionaria`
## Creazione tabelle:
### Proprietari
	CREATE TABLE Proprietari (
		id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
		nome VARCHAR(45),
		cognome VARCHAR(45),
		eta INT,
		sesso ENUM('M','F')
	);
| id | nome | cognome | eta | sesso |
|--|--|--|--|--|


### Automobili
	CREATE TABLE Automobili (
		id INT PRIMARY KEY,
		marca VARCHAR(50),
		modello VARCHAR(50),
		anno INT,
		colore VARCHAR(20),
		prezzo DECIMAL(10, 2),
		proprietario INT,
		FOREIGN KEY(proprietario) REFERENCES Proprietari (id)
	);
| id | marca| modello | anno | colore | prezzo | proprietario|
|--|--|--|--|--|--|--|
## Input Dati: 
### Proprietari
INSERT INTO `proprietari` (`nome`, `cognome`, `eta`, `sesso`) VALUES ('nome', 'cognome', 'eta', 'sesso');

| id | nome | cognome | eta | sesso |
|--|--|--|--|--|
| 1 | pippo | rossi | 15 | M |
| 2 | gianni | verdi | 23 | F |
| 3 | giannu | blu | 14 | F |
| 4 | giuseppe | rossi | 50 | M |
| 5 | gino | viola | 65 | M |

### Automobili

INSERT INTO `automobili` (`id`, `marca`, `modello`, `anno`, `colore`, `prezzo`, `proprietario`) VALUES ('id', 'marca', 'modello', 'anno', 'colore', 'prezzo', 'proprietario');)

| id | marca| modello | anno | colore | prezzo | proprietario|
|--|--|--|--|--|--|--|
| 1 | bmw | x4 | 2022 | blu | 4000.00 | 3 |
| 2 | mercedes | gg | 2021 | verde | 400000.00 | 5 |
| 3 | fiat | panda | 2000 | nera | 10000.00 | 1 |
 | 4 | tesla | hh | 200 | bianca | 10.00 | 4 |
 | 5 | audi | q5 | 20 | celeste | 100.00 | 2 |

## Query:
### Visualizza *proprietari* di automobili con *età maggiore di 20 anni*
`SELECT * FROM Proprietari WHERE eta>20;`
| id | nome | cognome | eta | sesso |
|--|--|--|--|--|
| 2 | gianni | verdi | 23 | F |
| 4 | giuseppe | rossi | 50 | M |
| 5 | gino | viola | 65 | M |

### Visualizza le *automobili* con *anno d'immatricolazione maggiore del 2010*
`SELECT * FROM Automobili WHERE anno>2010;`
| id | marca| modello | anno | colore | prezzo | proprietario|
|--|--|--|--|--|--|--|
| 1 | bmw | x4 | 2022 | blu | 4000.00 | 3 |
| 2 | mercedes | gg | 2021 | verde | 400000.00 | 5 |

### Visualizza tutte le *automobili*
`SELECT * FROM Automobili;`
| id | marca| modello | anno | colore | prezzo | proprietario|
|--|--|--|--|--|--|--|
| 1 | bmw | x4 | 2022 | blu | 4000.00 | 3 |
| 2 | mercedes | gg | 2021 | verde | 400000.00 | 5 |
| 3 | fiat | panda | 2000 | nera | 10000.00 | 1 |
 | 4 | tesla | hh | 200 | bianca | 10.00 | 4 |
 | 5 | audi | q5 | 20 | celeste | 100.00 | 2 |
