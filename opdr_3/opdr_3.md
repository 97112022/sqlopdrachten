# Sql basis

### Database
Maak gebruik van het sql-bestand idscan.sql en voer hierop onderstaande opdrachten uit.
Theorie kun je vinden op: https://www.edutorial.nl/dbq/introductie/

### CSV bestanden importeren
* Maak een database met de naam "superduper"
* Start mysql-server en log in met je gebruikersnaam en password
* Download de databestanden
* Voer het sql-script uit om de tabellen aan te maken in de database "superduper"
* Importeer de databestanden
* Exporteer de volledige database inclusief gegevens naar een .sql bestand (bijv. met mysqladmin)


CREATE DATABASE superduper; USE superduper
CREATE TABLE IF NOT EXISTS `superduper`.`persons` (`COL 1` varchar(2), `COL 2` varchar(5), `COL 3` varchar(14), `COL 4` varchar(33), `COL 5` varchar(52), `COL 6` varchar(31), `COL 7` varchar(19), `COL 8` varchar(19)) DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;; 
