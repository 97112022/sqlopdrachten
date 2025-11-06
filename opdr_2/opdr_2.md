# Sql basis

### Database gegevens aanpassen
Maak gebruik van het sql-bestand reisbureau.sql en voer hierop onderstaande opdrachten uit.
Theorie kun je vinden op: https://www.edutorial.nl/dbq/introductie/

### Opdracht 1
* Geef de query om alle tabellen in de database 'reisbureau' weer te gegeven
SHOW TABLES FROM reisbureau; 

### Opdracht 2
* Voeg 2 nieuwe klanten toe aan de tabel 'customers' (je mag de waarden zelf bedenken)
INSERT INTO `customers` (`id`, `first_name`, `last_name`, `email`, `address`, `postal_code`, `city`, `country_code`, `phone`, `created_at`, `updated_at`) VALUES (NULL, 'jesper', 'pot', 'jpot@gmail.com', 'batsstraat 33', '4721 HJ', 'Zwolle', 'nl_NL', '06-17283941', NULL, NULL), (NULL, 'niels', 'cracker', 'ncracker@deltion.nl', 'Koekenbakkerlaan 410', '5342 KK', 'Oldenzaal', 'nl_NL', '06-83622831', NULL, NULL);

### Opdracht 3
* Geef de query om de eerste 10 boekingen te verwijderen (reservations)


### Opdracht 4
* De klant met id 13 is verhuist naar 'De van der veldensteeg 81' in 'Apeldoorn'.
* Pas het record aan en geef de query
* Toon het record en controleer of de gegevens correct zijn.
