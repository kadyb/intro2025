# Projekt zaliczeniowy
## Implementacja funkcji

### Wprowadzenie

Dane wyrażone są zazwyczaj w różnych jednostkach i skalach. Przykładowo, wzrost
osoby (1,50-2,00 m) oraz jej wynagrodzenie (4000-20000 zł). Bezpośrednie
porównywanie takich zmiennych jest problematyczne, ponieważ zmienne o większym
zakresie liczbowym mogą dominować nad pozostałymi między innymi przy wizualizacji
danych. Aby rozwiązać ten problem, stosuje się normalizację danych. Jest to
matematyczne sprowadzenie wszystkich zmiennych do wspólnej, porównywalnej skali,
bez utraty informacji o relacjach między nimi. Dwie najpopularniejsze metody to:

- Normalizacja średnią (mean normalization) -- wartości zostają przeskalowane
względem średniej i rozstępu zbioru (różnica między wartością maksymalną a
minimalną). Średnia znormalizowanych wartości wynosi 0, a zakres mieści się w
przybliżonym przedziale od -1 do 1.
Wzór:

$$x_{norm} = \frac{x - \text{mean}(x)}{\max(x) - \min(x)}$$

- Normalizacja Z-score (Z-score normalization) – wartości zostają przeskalowane
w taki sposób, aby ich średnia wynosiła 0, a odchylenie standardowe 1.
Wartości zostają wyrażone jako liczba odchyleń standardowych od średniej.
Wzór:

$$x_{norm} = \frac{x - \text{mean}(x)}{\text{sd}(x)}$$

### Cel zadania

Napisz funkcję w języku R, która umożliwi normalizację wartości wektora
liczbowego za pomocą dwóch metod, tj. normalizacji średnią i normalizacji
Z-score. W zależności od zakresu wykonanych prac można otrzymać następujące
oceny:

### Ocena dostateczna

- Funkcja przyjmuje dwa argumenty: wektor liczbowy oraz parametr określający
metodę normalizacji.
- Kod zawiera przynajmniej jeden wartościowy komentarz.
- Oba wzory matematyczne zostały poprawnie zaimplementowane.
- Funkcja poprawnie zwraca znormalizowany wektor liczbowy.

### Ocena dobra

- Wykonanie wymagań na ocenę dostateczną.
- Walidacja danych wejściowych:
  - Sprawdzenie, czy są wektorem liczbowym.
  - Sprawdzenie, czy posiadają więcej niż jeden element.
  - Sprawdzenie, czy wartości są różne.
- Obsługa brakujących wartości (tj. dodanie parametru `na.rm` pozwalającego na
ignorowanie wartości *NA* podczas obliczeń).

### Ocena bardzo dobra

- Wykonanie wymagań na ocenę dostateczną oraz dobrą.
- Dokumentacja funkcji w formacie komentarzy *roxygen2* (należy udokumentować
tytuł, opis, parametry, zwracaną wartość oraz przykłady użycia używając
odpowiednich tagów).
- Funkcja zamiast samego wektora zwraca listę z nazwanymi elementami:
  - Znormalizowany wektor.
  - Użyta metoda.
  - Wartości statystyk wykorzystane do normalizacji (średnia, odchylenie
  standardowe, wartość maksymalna i minimalna).
- Napisanie prostych testów jednostkowych:
  - Poprawność wyników dla znanego wektora liczbowego.
  - Zwrócenie błędu dla nieprawidłowego typu danych.
  - Test brakujących wartości (*NA*).
  - Test wektorów o długości 1 lub o zerowej wariancji.
