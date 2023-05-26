# Creare un database 

```sql
CREATE DATABASE motorizzazione;
use motorizzazione;
```

# -Scriviamo le tabelle- 
## *automobile*
- Numero di Telaio
- Produttore auto
- Modello auto
- Codice fiscale del proprietario
- Anno di immatricolazione
- Numero cavalli
## *proprietario*
- Codice fiscale proprietrario
- Nome proprietario
- Cognome proprietario
- Età 
- data di nascita
- 
```sql
CREATE TABLE automobili (
n_telaio INT(10),
produttore VARCHAR(20) NOT NULL,
modello VARCHAR(10) NOT NULL,
proprietario VARCHAR(10) NOT NULL,
anno_immatricolazione INT(4) NOTNULL,
n_cavalli INT(3) NOT NULL,
 PRIMARY KEY (n_telaio)
);

CREATE TABLE proprietari (
id_proprietario VARCHAR(10),
nome VARCHAR(18) NOT NULL,
cognome VARCHAR(10) NOT NULL,
eta INT(2) NOT NULL,
data_nascita DATE NOT NULL,
PRIMARY KEY (id_proprietario)
);
```
## -Riempiamo le tabelle-
_automobile_:
| Numero telaio | Produttore | Modello | Proprietario | Anno immatricolazione| Numero Cavalli | 
| ------ | ------ |------ | ------ |------ | ----- |
| 1526784658 | Nissan | Leaf | FRNFTZ92E26F257T | 1999 | 217 |
|  1548963324 | Opel | Astra | GSPCNN00R07E715C | 2014 | 220 |
|  1563255842 | Fiat | Punto | GRGBCH90D18L781O | 2008 | 150 |
|  1575365412 | Toyota | Aygo | GNNSRT02H20F839I | 2005 | 110 |
|  1575416855 | Chevrolet | Avea | CVLPTR04D26A669R | 2012 | 309 |
_proprietari_:
| Codice Fiscale | Nome | Cognome | Età | data di nascita | 
| ------ | ------ |------ | ------ |------ | 
| FRNFTZ92E26F257T | Franco | Fittizio | 31 | 26/05/1992 |
|  GSPCNN00R07E715C | Giuseppe | Cannone | 23 | 07/10/2000 | 
|  GRGBCH90D18L781O | Giorgio | Baschirotto | 33 | 18/04/1990 |
|  GNNSRT02H20F839I | Gianni | Strorti | 20 | 20/06/2002 |
| CVLPTR04D26A669R | Pietro | cavaliere | 19 | 26/04/2004 |

```sql

INSERT INTO automobili(n_telaio, produttore, modello, proprietario, anno_immatricolazione, n_cavalli)
VALUES( 1526784658, "Nissan", "Leaf", "FRNFTZ92E26F257T", 1999, 217);

INSERT INTO automobili(n_telaio, produttore, modello, proprietario, anno_immatricolazione, n_cavalli)
VALUES( 1548963324, "Opel", "Astra", "GSPCNN00R07E715C", 2014, 220);

INSERT INTO automobili(n_telaio, produttore, modello, proprietario, anno_immatricolazione, n_cavalli)
VALUES( 1563255842, "Fiat", "Punto", "GRGBCH90D18L781O", 2008, 150);

INSERT INTO automobili(n_telaio, produttore, modello, proprietario, anno_immatricolazione, n_cavalli)
VALUES( 1575365412, "Toyota", "Aygo", "GNNSRT02H20F839I", 2005, 110);

INSERT INTO automobili(n_telaio, produttore, modello, proprietario, anno_immatricolazione, n_cavalli)
VALUES( 1575416855, "Chevrolet", "Aveo", "CVLPTR04D26A669R", 2012, 309);

INSERT INTO proprietari(id_proprietario, nome, cognome, eta, data_nascita)
VALUES( "FRNFTZ92E26F257T", "Franco", Fittizio, 31, 26/05/1992);

INSERT INTO proprietari(id_proprietario, nome, cognome, eta, data_nascita)
VALUES( "GSPCNN00R07E715C", "Giuseppe", "Cannone", 23, 07/10/2000);

INSERT INTO proprietari(id_proprietario, nome, cognome, eta, data_nascita)
VALUES( "GRGBCH90D18L781O", "Giorgio", "Baschirotto", 33, 18/04/1990);

INSERT INTO proprietari(id_proprietario, nome, cognome, eta, data_nascita)
VALUES( "GNNSRT02H20F839I", "Gianni", "Storti", 20, 20/06/2002);

INSERT INTO proprietari(id_proprietario, nome, cognome, eta, data_nascita)
VALUES( "CVLPTR04D26A669R", "Pietro", "Cavaliere", 19, 26/04/2004);
```
## -Controlliamo quali proprietari hanno più di 20
```sql 
SELECT * FROM proprietari WHERE eta>20;
```
## -Controlliamo quali auto sono state immatricolate dopo il 2010
```sql 
SELECT * FROM automobili WHERE anno_immatricolazione > 2010
```





