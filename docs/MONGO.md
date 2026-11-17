# Podręcznik Konfiguracji MongoDB

## 1. Wybór środowiska

### Opcja Chmurowa: MongoDB Atlas (Zalecane)
Darmowa instancja w chmurze (M0 Sandbox), która nie obciąża procesora maszyny Minecraft:
1. Przejdź do [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
2. Stwórz darmowy klaster M0.
3. W sekcji **Database Access** stwórz użytkownika bazy (np. `blockcode_user`).
4. W sekcji **Network Access** kliknij **Add IP Address** i dodaj `0.0.0.0/0` (zezwolenie na połączenia z zewnątrz).
5. Wybierz **Database -> Connect -> Drivers** i skopiuj uzyskany adres URI:
   `mongodb+srv://blockcode_user:HASLO@twoj-klaster.mongodb.net/`

### Opcja Lokalna: Docker
```bash
docker run -d \
  --name blockcode-mongo \
  -p 27017:27017 \
  -v mongo_data:/data/db \
  --restart always \
  mongo:latest
```

URI dla instancji Docker na tej samej maszynie:
`mongodb://localhost:27017`

## 2. Optymalizacja i Indeksy

Po zainstalowaniu skryptu zaleca się utworzenie unikalnego indeksu w MongoDB Compass lub powłoce `mongosh`, aby wyszukiwanie UUID było błyskawiczne:

```javascript
use blockcode;
db.players.createIndex({ "uuid": 1 }, { unique: true });
db.warps.createIndex({ "name": 1 }, { unique: true });
```

## 3. Diagnostyka

Komenda serwerowa:

/bca status

Wypisuje aktualny stan klienta MongoSK. W przypadku braku połączenia sprawdź:
- Poprawność znaków specjalnych w haśle.
- Zezwolenia zapory sieciowej (Port 27017).
- Wersję silnika (wymagany MongoSK 2.x).

