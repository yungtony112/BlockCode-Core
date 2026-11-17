# Przewodnik Instalacji — BlockCode-Core (v1.0-SNAPSHOT)

Przewodnik instalacji dla maszyn lokalnych (**Localhost**) oraz zdalnych **Hostingów Minecraft**.


## Krok 1: Weryfikacja środowiska serwera

Upewnij się, że Twój serwer uruchamia silnik **Paper**, **Purpur** lub **Spigot** w wersji **1.21 lub nowszej**.(starsze wersje nie były testowane więc mogą byc niestabilne)

Pobierz i umieść w katalogu `/plugins/`:
1. **[Skript 2.7+](https://github.com/SkriptLang/Skript)**
2. **[MongoSK 2.x](https://github.com/Romitou/MongoSK)**

Zrestartuj serwer, aby wygenerować foldery konfiguracyjne pluginów.

## Krok 2A: Instalacja na maszynie lokalnej (Localhost)

1. Upewnij się, że lokalna usługa MongoDB działa na Twoim komputerze na domyślnym porcie `27017`.
2. Skopiuj plik `BlockCode-Core.sk` do ścieżki:
   `plugins/Skript/scripts/BlockCode-Core.sk`
3. Otwórz plik i upewnij się, że nagłówek konfiguracji zawiera:
   ```yaml
   options:
       mongo-uri: mongodb://localhost:27017
       mongo-database: blockcode
   ```
4. Wpisz w konsoli serwera:
   ```text
   sk reload BlockCode-Core
   ```
5. Konsola powinna zwrócić:
   `[BlockCode] MongoDB connected! DB: blockcode`


## Krok 2B: Instalacja na wykupionym Hostingu (Pterodactyl / Multicraft)

Hostingi współdzielone najczęściej blokują lokalne bazy danych, dlatego najlepszym rozwiązaniem jest darmowa baza **MongoDB Atlas**:

1. Skonfiguruj darmowy klaster w [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
2. Pobierz swój adres Connection String, np.:
   `mongodb+srv://admin:MojeBezpieczneHaslo123@cluster0.abcde.mongodb.net/`
3. Wejdź do panelu hostingu Minecraft, przejdź do File Managera i wejdź w:
   `/plugins/Skript/scripts/`
4. Wgraj tam plik `BlockCode-Core.sk`.
5. Dokonaj edycji pliku bezpośrednio w edytorze panelu hostingu:
   ```yaml
   options:
       mongo-uri: mongodb+srv://admin:MojeBezpieczneHaslo123@cluster0.abcde.mongodb.net/
       mongo-database: blockcode
   ```
6. Zapisz plik i przeładuj skrypt w konsoli hostingu:
   ```text
   sk reload BlockCode-Core
   ```

## Krok 3: Weryfikacja działania

Wpisz w grze komendę:
```text
/bca status
```
Powinieneś zobaczyć zielony komunikat o aktywnym połączeniu.

Wykonaj serię testów:
1. Ustaw spawn komendą `/setspawn`.
2. Dodaj środki do konta komendą `/money give TwójNick 500`.
3. Zrestartuj serwer.
4. Po ponownym wejściu sprawdź stan konta (`/money`) oraz wpisz `/spawn`. Wszystkie dane zostaną bezbłędnie załadowane z MongoDB.
```