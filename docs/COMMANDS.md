# Lista Komend — BlockCode-Core

## Nawigacja i Teleportacja

Komendy i opisy
 `/home [nazwa]` | Teleportacja do wskazaneg domu (domyślnie "home") 
 `/sethome [nazwa]` -  Zapisanie lokalizacji pod daną nazwą 
 `/delhome [nazwa]` -  Usunięcie wybranegp domu 
 `/homes` -  Lista Twoich zapisanych domów
 `/tpa <gracz>` -  Wysłanie zapytania o teleportację 
 `/tpaccept` -  Akceptacja oczekującej prośby o teleportację 
 `/tpdeny` -  Odrzucenie oczekującej prośby 
 `/warp [nazwa]` -  Teleportacja do warpu (brak argumentu wyświetla listę) 
 `/setwarp <nazwa>` -  Utworzenie nowego warpu serwerowego 
 `/delwarp <nazwa>` -  Usunięcie istniejącego warpu 
 `/spawn` -  Teleportacja na spawn z 3-sekundowym oczekiwaniem 
 `/setspawn` -  Ustawienie punktu odrodzenia serwera 
 `/rtp` -  Losowy skok w bezpieczne koordynaty mapy 
 `/back` -  Powrót do koordynatów ostatniego zgonu 

## Gospodarka i Portfel

Komendy i opisu
 `/money` -  Sprawdzenie stanu konta 
 `/money pay <gracz> <kwota>` -  Przelanie środków do innego użytkownika 
 `/money top` -  Ranking 10 najbogatszych kont w bazie 
 `/money set <gracz> <kwota>` -  Ustawienie stanu konta gracza (Admin) 
 `/money give <gracz> <kwota>` -  Dodanie środków do konta gracza (Admin) 
 `/money take <gracz> <kwota>` -  Zmniejszenie bilansu konta gracza (Admin) 

## Komunikacja

Komendy i opisu
 `/msg <gracz> <wiadomosc>` -  Wysłanie prywatnej wiadomości 
 `/reply <wiadomosc>` -  Szybka odpowiedź na ostatni szept 
 `/profile [gracz]` -  Wyświetlenie szczegółowych statystyk 
 `/afk` -  Ręczne oznaczenie statusu nieobecności 
 `/chatcolor <kod>` -  Zmiana domyślnego koloru wypowiedzi na czacie 

## Narzędzia Użytkowe

Komendy i opisu
 `/menu` -  Otwarcie graficznego interfejsu (GUI) 
`/rename <nazwa>` -  Zmiana nazwy trzymanego itemu za opłatą 50 monet 
`/ec` -  Otwarcie enderchesta z poziomu komendy 
`/skull <gracz>` -  Wydanie głowy danego gracza 
`/heal [gracz]` -  Wyleczenie życia i głodu 
`/feed [gracz]` -  Uzupełnienie punktów nasycenia i głodu 
`/gm <0-3>` -  Zmiana trybu gry (0=Survival, 1=Creative, 2=Adventure, 3=Spectator) 
`/help` -  Zestawienie dostępnych komend 

## Panel Administracyjny
Komendy i opisu
 `/bca status` - Sprawdzenie aktywności połączenia z MongoDB 
 `/bca save` -  Wymuszenie natychmiastowego zapisu pamięci do bazy 
 `/bca reload` -  Załadowanie świeżych dokumentów z MongoDB 
 `/bca purge` -  Wyczyszczenie zmiennych sesji walki i teleportacji 
 `/bca dbstats` -  Liczba graczy, suma waluty i dokumentów w MongoDB 

