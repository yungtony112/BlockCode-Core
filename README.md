# BlockCode-Core `v1.0-SNAPSHOT`

![Version](https://img.shields.io/badge/version-1.0--SNAPSHOT-1E90FF?style=flat-square)
![Minecraft](https://img.shields.io/badge/Minecraft-1.21+-2E8B57?style=flat-square)
![Skript](https://img.shields.io/badge/Skript-2.7+-007ACC?style=flat-square)
![Database](https://img.shields.io/badge/Database-MongoDB-47A248?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

Kompletny, wydajny silnik serwerowy w Skript zintegrowany bezpośrednio z nierelacyjną bazą danych **MongoDB** za pośrednictwem pluginu **MongoSK**.

## Moduly

- **Custom Economy** - portfel, przelewy, top 10
- **Multi-Homes** - domy graczy zapisywane w MongoDB jako lokacje z podziałem na rangi
- **Combat Log** - blokada wylogowywania podczas pvp, pasek walki, kary
- **Random Teleport (RTP)** - bezpieczne algorytmy wyszukiwania stałego lądu
- **TPA Engine** - zaproszenia do teleportacji z czasem wygasania
- **Chat Management** - system rang, formatowanie, ochrona przed spamem, wywoływanie graczy
- **Player Stats** - zabójstwa, śmierci, K/D ratio, serie, czas gry, wykopane bloki
- **Warps & Spawn** - dynamiczne punkty teleportacji zapisywane w bazie
- **Admin Tools** - komendy serwisowe z inspekcją stanu bazy `/bca`

## Architektura danych

Wszystkie dane runtime są trzymane w szybkiej pamięci RAM, a operacje krytyczne oraz okresowe synchronizują się z MongoDB:


[ Gracz dołącza ]  ---> Odczyt z kolekcji MongoDB do RAM
[ Gra na serwerze] ---> Błyskawiczny odczyt/zapis w RAM
[ Auto-save 5m ]   ---> Zrzut zmiennych do kolekcji MongoDB
[ Wyjście gracza ] ---> Zapis danych i usunięcie śmieci z pamięci


## Dokumentacja

- [Instrukcja instalacji (Localhost & Hosting)](docs/INSTALLATION-GUIDE.md)
- [Pełna lista komend](docs/COMMANDS.md)
- [Uprawnienia (Permissions)](docs/PERMISSIONS.md)
- [Struktura funkcji i baza danych](docs/FUNCTIONS.md)
- [Konfiguracja bazy MongoDB](docs/MONGO.md)

## Wymagania

- Paper / Purpur / Spigot **1.17+**
- Java **17+**
- [Skript 2.7+](https://github.com/SkriptLang/Skript)
- [MongoSK 2.x](https://github.com/Romitou/MongoSK)
- Instancja MongoDB (lokalna lub MongoDB Atlas)

