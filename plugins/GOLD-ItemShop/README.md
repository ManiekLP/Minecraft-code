# Plugin na ItemShop

**Opis:**
--------
- W miare prosty plugin na itemshop z łatwą możliwością edytowania każdej usługi w pliku `items.yml`

**Wymagania**
--------
- BazaDanych MySql

**Komendy:**
--------
- `/odbierz` -  odbiór nagród
- `/is` - opis
- `/is reload` - przeładowanie configu
- `/is list` - lista usług
- `/is nadaj <gracz> <usluga>` - nadanie usługi danemu graczowi
- `/is create <nazwa> [<komenda>]` - tworzy nową usługe w pliku items.yml z daną nazwą. i itemkiem podglądowym trzyumanym w łapie!

**Permisje:**
--------
- `gold.itemshop.admin`- umożliwia dostęp do komendy administracyjnej 
- `gold.itemshop.use` - daje dostęp do `/odbierz`

**Zmienne:**
--------
Plugin obsługuje kilka zmiennych do usprawnienia działania komend. Zmienne dostępne do użycia:
- `%PLAYER%` - Wyświetla nazwę gracza.
- `%SERVICE%` - Wyświetla nazwe usługi.

**Wyjaśnienie ustawień z pliku `Items.yml`**
--------
Jakby ustawienie usług w plikach było ciężkię to śpieszę z pomocą:
- `key: ` - nazwa usługi po dodaniu usługi lepiej nie zmieniać.
- `instant: ` - Jeśli ta zmienna jest ustawiona na `true` to komendy zostaną wykonane odrazu po nadaniu. Jeśli jednak będzie ustawione na `false` to usługa zostanie dodana graczowi do `/odbierz` i gracz może sobie odebrać dane itemki z komendy w późniejszym czasie.
- `name: ` - Jest to nazwa wyświetlana w wiadomości na chacie po zakupie.
- `itemStack: ` - Jest to przedmiot odpowiadający za wygląd usługi w gui pod `/odbierz`. Jeśli `instance` jest ustawione na true ten warunek jest pomijany (Wtedy najlepiej ustawić `Material` na `BARRIER`).
- `commands: ` - Komendy wykonane po odebraniu usługi.

**Przykład ustawienia pliku `itmes.yml`:**
--------
```
items:
  vip30d:
    key: vip30d
    instant: true
    name: &6VIP na 30 dni
    itemStack:
      material: BARRIER
    commands:
    - lp %PLAYER% parent addtemp vip 30d
  LegeKey:
    key: LegeKey
    instant: false
    name: &ePakiet Legendarnych Kluczy
    itemStack:
      material: TRIPWIRE_HOOK
      item-meta:
        display-name: '&eLegendarny Klucz'
        lore:
        - '&7Kluczyk do &eLegendarnej skrzyni'
        - '&7Kluczyk możesz zakupić na &c&nexample.com&c&n'
    commands:
    - case give %PLAYER% 4
```

**Wersja:**
--------
- Każda wersja powinna działać! Polecana 1.18.2

Support:
--------
**If you notice any errors, please contact me on Discord!**
- **[Support Discord](https://discord.gg/94qhBxDEv8)**
- **[Author Discord](https://discord.com/users/431183447667638272)**
