# Labo-4---Connection

In dit labo leer je hoe je de ADO.NET Connected Classes gebruikt om te werken met een SQL Server database. Je leert hoe je verbinding maakt met de database, gegevens invoegt, verwijdert en uitleest met behulp van SqlCommand, SqlDataReader en SqlParameter.

## Deel 1: SqlConnection

### Database aanmaken
Maak een nieuwe database aan in SQL Server met de naam LaboDB.

Gebruik het volgende script om de FootballClubs tabel aan te maken en demo data in te voegen:
```
-- Create Table Script
CREATE TABLE FootballClubs (
    ClubId INT PRIMARY KEY IDENTITY(1,1),
    ClubName NVARCHAR(100) NOT NULL,
    Country NVARCHAR(50),
    FoundedYear INT,
    StadiumName NVARCHAR(100),
    Capacity INT
);

-- Insert Seed Data
INSERT INTO FootballClubs (ClubName, Country, FoundedYear, StadiumName, Capacity)
VALUES
('FC Barcelona', 'Spain', 1899, 'Camp Nou', 99354),
('Manchester United', 'England', 1878, 'Old Trafford', 74879),
('Real Madrid', 'Spain', 1902, 'Santiago Bernabéu', 81044),
('Liverpool', 'England', 1892, 'Anfield', 53394),
('Juventus', 'Italy', 1897, 'Allianz Stadium', 41507),
('Bayern Munich', 'Germany', 1900, 'Allianz Arena', 75024),
('Arsenal', 'England', 1886, 'Emirates Stadium', 60704);
```

### Connectionstring instellen
- Zoek de connectiestring naar LaboDB in SQL Server Management Studio (SSMS).
- Zet deze connectiestring in de App.config of Settings.settings file van je C# project.

### Verbinding maken
Schrijf code in C# om succesvol een verbinding te openen met LaboDB.

## Deel 2: SqlCommand

### INSERT
Maak een hardcoded INSERT-query met een SqlCommand die een nieuwe club toevoegt.

### DELETE
Verwijder Arsenal uit de tabel met behulp van een SqlCommand en SqlParameter.

## Deel 3: SqlParameter
### UPDATE
Implementeer een methode ``UpdateCapacityById(int id, int capacity)`` die de capaciteit voor de club met de gegeven id update met de nieuwe waarde voor capacity.

Zorg er voor dat de gebruiker de waardes voor id en capacity kan ingeven en gebruik een try catch waar nodig.

## Deel 4: SqlDataReader
### SELECT
- Maak een FootballClub object met properties gelijkaardig aan de kolommen uit de tabel.
- Lees alle rijen uit en maak er objecten van.
- Voorzie een `ToString()` functie in de FootballClub klasse en print alle FootballClub objecten af.

