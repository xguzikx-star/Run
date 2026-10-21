# Śródziemie — Droga Pierścienia (v0.1)

Mobilna aplikacja PWA na iPhone'a, hostowana na GitHub Pages. Rejestruje marsz, bieg i interwały (szybko lub szczegółowo); oblicza trasę w skali **1 km realny = 3 km fabularne**; pokazuje kronikę odkryć, tygodniowy wykres dystansu oraz serię tygodniową. Umożliwia dodawanie starszych treningów, edycję, usuwanie, eksport i import JSON.

## Instalacja na GitHub Pages

1. Utwórz repozytorium, np. `srodziemie`, i wgraj **zawartość** tego folderu do katalogu głównego repozytorium (index.html musi być w root).
2. Wejdź do **Settings → Pages → Build and deployment → Deploy from a branch**, wybierz `main`, katalog `/ (root)` i zapisz.
3. Otwórz adres `https://NAZWA-UZYTKOWNIKA.github.io/srodziemie/` w Safari na iPhonie.
4. W Safari wybierz **Udostępnij → Dodaj do ekranu początkowego**.

Działa jako statyczna strona (nie wymaga backendu). Możesz także uruchomić lokalny serwer, np. `python -m http.server 8000`, i otworzyć `http://localhost:8000` na komputerze. Otwieranie index.html przez `file://` nie gwarantuje instalacji PWA ani działania service workera.

## Dane i kopie

Dane treningowe zapisują się w `localStorage` danej instalacji przeglądarki. **Nie synchronizują się** przez GitHub ani między urządzeniami. Korzystaj z ikony ustawień → „Pobierz kopię JSON”. Przywracanie kopii **zastępuje** istniejące dane. Nie przechowuj prywatnego JSON w publicznym repozytorium. Wyczyszczenie danych strony może usunąć dziennik.

## Znane ograniczenia

- **Kartografia v0.1 jest stylizowaną mapą SVG, a nie geograficznie dokładną mapą Tolkiena.** Kilometraż punktów pośrednich i podział trasy to wartości robocze, wymagające weryfikacji w jednej konsekwentnej rekonstrukcji. Przyjęte kotwice: 0 / 737 / 1481 / 2107 / 2863 km fabularnych.
- Karty odkryć zawierają krótkie autorskie opisy; ilustracje miejsc i komplet badań źródłowych to następna iteracja.
- Wersja v0.1 nie ma automatycznego importu treningów ze smartwatcha, synchronizacji, testów na urządzeniach ani kolejnych wypraw.
- Po zapisie segmentów treningu dystans pozostaje wpisaną wartością z bieżni. Tempo liczone jest jako czas/dystans, nie z sumy prędkości segmentów.
- Po zmianie danych odznaki odkryć przeliczane są z bieżącego kilometrażu.

## Struktura

`index.html` · `style.css` · `app.js` · `sw.js` · `manifest.webmanifest` · `assets/`

Kod bez frameworka i kompilatora — wygodny do kolejnych iteracji i publikacji bez builda.
