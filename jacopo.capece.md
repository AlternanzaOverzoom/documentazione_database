


# Database Schema

## Creazione Database
```sql
CREATE DATABASE carrozaio;
USE carrozaio;
CREATE TABLE Automobiles(
    marca VARCHAR(50) NOT NULL,
    modello VARCHAR(50) NOT NULL,
    telaio VARCHAR(50) NOT NULL,
    immatricolazione DATE NOT NULL,
    portiere INT NOT NULL,
    PRIMARY KEY(telaio)
);

CREATE TABLE Owners(
    nome VARCHAR(50) NOT NULL,
    cognome VARCHAR(50) NOT NULL,
    ticketRicevuto VARCHAR(50) NOT NULL,
    telefono INT(25) NOT NULL,
    eta INT(2) NOT NULL,
    FOREIGN KEY(ticketRicevuto) REFERENCES Automobiles(telaio)
);


-- Visualizzazione auto immatricolate dopo il 2010
SELECT * FROM Automobiles WHERE immatricolazione > '2010-01-01';

-- Visualizzazione di tutte le auto
SELECT * FROM Automobiles;

-- Visualizzazione di tutti i proprietari
SELECT * FROM Owners;
```
# TABELLE
## Automobiles


|marca| modello | telaio | immatricolazione |portiere |
|--|--|--|--|--|
|Nissan  | Qashqai|1vtuv1u232xxx|9/11/2010|5|
|Nissan|supra|21g1nc98122|12/12/2012|3|
|Lamborghini|lambda|r267qecvbfqu|20/04/1999|4|
|Ferrari|499p|61ebd6wq|26/05/2023|2|
|Nissan|qashquai|51286tb12c8n21|13/05/2005|5|

## Owners

|nome| cognome | telefono | eta | ticketRicevuto |
|--|--|--|--|--|
|Francesco | Totti|516284512|19|afsvdiasvbcsac|
|Pietro|Mennea|541928468124|44|512351gasxnag|
|Roberto|Spontino|12736104|33|dh72bwqgwqgd9|
|Carmela|Cantatore|14971419284|76|iauichadw87a7|
|Francesca|Rossi|5613805610|18|1286yedh8d1n0|