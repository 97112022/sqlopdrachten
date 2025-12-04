# Sql basis

### Database
Maak gebruik van het sql-bestand flits.sql en voer hierop onderstaande opdrachten uit.
Theorie kun je vinden op: https://www.edutorial.nl/dbq/introductie/

### Queries flitspaal
* Welke cameras zijn er en waar staan ze (id, address, city, max_speed).
SELECT * FROM `cameras` WHERE 1; 

* Overzicht van boetes op 50km wegen
SELECT fine FROM `fines` WHERE fines.speed_limit = 50; 

* Overzicht van overtredingen van 1 kenteken.
SELECT * FROM `flashes` WHERE license = "F-943-VP"; 

* N.a.w.-gegevens van de hardrijders die het meest in de fout zijn gegaan. (top 10)
SELECT licenses.first_name, licenses.last_name, licenses.address, licenses.postal_code, licenses.city, COUNT(flashes.license) AS OVERTREDINGEN
FROM licenses
JOIN flashes ON flashes.license = licenses.license
GROUP BY flashes.license
ORDER by OVERTREDINGEN DESC
LIMIT 10

* Welke camera’s (id, address, city) meten de meeste snelheidsovertredingen (top 10)
SELECT cameras.address, cameras.id, cameras.city, COUNT(flashes.camera_id) AS OVERTREDINGEN FROM cameras JOIN flashes ON cameras.id = flashes.camera_id GROUP BY flashes.camera_id ORDER by OVERTREDINGEN DESC LIMIT 10; 

* Welke auto’s (kenteken, merk, type) zijn het meeste geflitst


* Welke flitspaal (=camera met id, address, city) flitst het meest (top 10)
SELECT cameras.address, cameras.id, cameras.city, COUNT(flashes.camera_id) AS FLITSEN FROM cameras JOIN flashes ON cameras.id = flashes.camera_id GROUP BY flashes.camera_id ORDER by FLITSEN DESC LIMIT 10; 


* Kentekens van auto’s die het hoogste bedrag aan boetes hebben gekregen (top 10)
SELECT SUM(fines.fine) as Totaalboete, flashes.license FROM `fines` JOIN cameras on cameras.max_speed = fines.speed_limit JOIN flashes on flashes.camera_id = cameras.id GROUP by flashes.license ORDER by Totaalboete DESC limit 10; 

* Overzicht van auto’s (kenteken, merk, type) waarvan het kenteken overeenkomt met sitecode 10 (zoals X-999-XX) https://nl.wikipedia.org/wiki/Nederlands_kenteken.

SELECT licenses.license FROM `licenses`
WHERE licenses.license like '_-___-__';