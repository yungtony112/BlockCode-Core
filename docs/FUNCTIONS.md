# Dokumentacja Funkcji i Schemat MongoDB

## Metody Sterownika MongoSK

### Inkrementacja i Liczby
mongoIncPlayer(uuid: text, key: text, amount: number)

Wykorzystuje operator `$inc` silnika MongoDB do natychmiastowego, atomowego zwiększenia licznika o podaną wartość bez ryzyka kolizji wątków.

### Serializacja Lokacji
mongoSaveLocation(uuid: text, key: text, loc: location)
mongoGetLocation(uuid: text, key: text) :: location

Minecraftowe obiekty lokalizacji są konwertowane do postaci płaskiego ciągu:
`X;;Y;;Z;;WORLD;;YAW;;PITCH`

Dzięki temu silnik MongoDB zapisuje je natywnie jako proste pola tekstowe o małej wadze.

## Schemat Dokumentów Bazy Danych

### Kolekcja: `players`
```json
{
  "_id": { "$oid": "6512bd89f1a23c4d5e6f7a8b" },
  "uuid": "4c8f5d02-1234-4567-890a-bcdef1234567",
  "name": "Kowalski",
  "balance": 1500,
  "kills": 12,
  "deaths": 4,
  "streak": 2,
  "mobKills": 85,
  "blocksBroken": 1420,
  "blocksPlaced": 612,
  "playtime": 7200,
  "joins": 15,
  "combatlogs": 0,
  "chatcolor": "&b",
  "homes": {
    "baza": "120.5;;64.0;;-320.5;;world;;90.0;;0.0",
    "kopalnia": "540.0;;12.0;;89.5;;world;;180.0;;15.0"
  }
}
```

### Kolekcja: `warps`
```json
{
  "_id": { "$oid": "6512bd89f1a23c4d5e6f7a8c" },
  "name": "arena",
  "location": "0.5;;70.0;;0.5;;world;;0.0;;0.0",
  "creator": "Admin"
}
```

### Kolekcja: `server`
```json
{
  "_id": { "$oid": "6512bd89f1a23c4d5e6f7a8d" },
  "key": "spawn",
  "value": "100.5;;65.0;;100.5;;world;;90.0;;0.0"
}
```
