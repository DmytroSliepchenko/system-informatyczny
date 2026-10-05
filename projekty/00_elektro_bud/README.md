1.Analiza wymagań. Magazyn Elektro-Bud

2.Wymagania funkcjonalne

2.1. FR.01. Logowanie i konta. Logowanie na login i hasło lub kartę RFID. Każdy pracownik ma własne konto, żeby było wiadomo, kto co robił.
2.2. FR.02. Wyszukiwanie towaru. Szukanie po kodzie EAN, po nazwie albo po obu naraz.
2.3. FR.03. Lokalizacja towaru. Pokazywanie gdzie leży towar, kod 6-znakowy: Sektor, Regał, Półka, na przykład S1R2P3.
2.4. FR.04. Przyjęcie towaru. Dodawanie towaru do stanu magazynu. Zapisuje ilość, kto dodał i kiedy.
2.5. FR.05. Wydanie towaru. Zmniejszanie stanu magazynu przy wydaniu towaru klientowi.
2.6. FR.06. Blokada braku towaru. System nie pozwala wydać więcej towaru niż jest na magazynie. Brak ujemnych stanów.
2.7. FR.07. Edycja produktów. Dodawanie nowych produktów i zmiana ich danych przez Kierownika.
2.8. FR.08. Historia operacji. Kierownik widzi pełną historię: kto, kiedy i co przyjął lub wydał.
2.9. FR.09. Raporty. Generowanie prostych raportów ze stanów magazynowych.
2.10. FR.10. Konta użytkowników. Administrator dodaje nowe konta, zmienia uprawnienia i resetuje hasła.
2.11. FR.11. Obsługa jednoczesnych operacji. Zabezpieczenie przed błędem, gdy dwóch magazynierów wydaje ten sam towar w tym samym czasie.

3.Wymagania niefunkcjonalne

3.1. NFR.01. Czas reakcji. System odpowiada szybko, do 1 lub 2 sekund przy szukaniu i skanowaniu.
3.2. NFR.02. Bezpieczeństwo. Hasła są szyfrowane. Nie ma wspólnych kont dla kilku osób.
3.3. NFR.03. Uprawnienia. Magazynier, Kierownik i Admin mają dostęp tylko do swoich funkcji.
3.4. NFR.04. Dostęp zdalny. Kierownik może sprawdzić raporty także poza magazynem.
3.5. NFR.05. Interfejs. Prosty, blokowy wygląd bez zbędnych grafik, wygodny do szybkiej pracy.

4.Aktorzy systemu

4.1. Magazynier. Loguje się, szuka towaru, sprawdza półki oraz rejestruje przyjęcia i wydania.
4.2. Kierownik magazynu. Zarządza listą produktów, przegląda historię operacji i generuje raporty.
4.3. Administrator. Tworzy konta dla pracowników, nadaje uprawnienia i resetuje hasła.

5.Diagram przypadków użycia. Połączenia

5.1. Magazynier połączony z: Logowanie, Wyszukiwanie towaru, Sprawdzenie lokalizacji, Przyjęcie towaru, Wydanie towaru.
5.2. Kierownik magazynu połączony z: Logowanie, Wyszukiwanie towaru, Edycja bazy produktów, Historia operacji, Raporty.
5.3. Administrator połączony z: Logowanie, Zarządzanie kontami.
5.4. Przyjęcie towaru oraz Wydanie towaru zawierają relację include do: Sprawdzenie dostępności.
5.5. Wydanie towaru zawiera relację extend do: Blokada ujemnego stanu.

6.Relacje include oraz extend

6.1. Relacja include, czyli wymagane. Operacje Przyjęcie towaru oraz Wydanie towaru zawsze wymagają wykonania Sprawdzenia dostępności. System musi za każdym razem zweryfikować stan bazy danych.
6.2. Relacja extend, czyli opcjonalne lub warunkowe. Przypadek Blokada ujemnego stanu rozszerza Wydanie towaru. Uruchamia się tylko wtedy, gdy magazynier próbuje wydać więcej towaru niż jest na stanie lub przy próbie jednoczesnego wydania przez 2 osoby
