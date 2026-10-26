# Kalibracja kamery

Historyczne zdjęcia wykonano kamerą fotogrametryczną:

- **kamera:** Wild RC10,
- **obiektyw:** Universal Aviogon II,
- **numer obiektywu:** 3008,
- **data kalibracji:** 29 sierpnia 1974.

## Parametry kalibracyjne

**Skalibrowana ogniskowa:** 153,02 mm

**Punkt główny PPA:**

| Parametr |   Wartość |
| -------- | --------: |
| X        | -0,004 mm |
| Y        | -0,010 mm |

## Znaki tłowe

Odległości pomiędzy czterema narożnymi znakami tłowymi:

| Odcinek |    Długość |
| ------- | ---------: |
| 2–3     | 212,011 mm |
| 3–4     | 212,015 mm |
| 4–1     | 212,013 mm |
| 1–2     | 212,016 mm |

Przybliżone współrzędne użyte w modelu kamery:

| Znak        |   X [mm] |   Y [mm] |
| ----------- | -------: | -------: |
| górny lewy  | -106,005 |  106,008 |
| górny prawy |  106,005 |  106,007 |
| dolny prawy |  106,007 | -106,007 |
| dolny lewy  | -106,007 | -106,008 |

## Dystorsja radialna

| Promień [mm] | Dystorsja [µm] |
| -----------: | -------------: |
|           20 |             -1 |
|           40 |              0 |
|           60 |             +1 |
|           80 |             +1 |
|          100 |             +1 |
|          120 |             -2 |
|          140 |             -1 |
|          148 |             +2 |

Współczynniki dystorsji radialnej zostały wyznaczone przez CATALYST na podstawie tabeli.

Parametry dystorsji decentrującej pozostawiono na wartości `0`, ponieważ nie były podane w dokumentacji kalibracyjnej.

## Orientacja skanu

Przyjęto:

`Calibration edge = Right`

Na prawej krawędzi skanu znajdował się pasek informacyjny zawierający m.in. numer obiektywu `3008` oraz ogniskową `153.02`.

## Znaki tłowe — wynik

Po ręcznym wyznaczeniu znaków na jednym zdjęciu wykorzystano automatyczną detekcję `AUTOFID`.

Końcowe błędy:

| Zdjęcie | Błąd [px] |
| ------- | --------: |
| 301     |      0,86 |
| 302     |      0,90 |
| 303     |      0,65 |
| 378     |      0,91 |
| 379     |      0,74 |
| 380     |      0,68 |
| 427     |      0,07 |
| 428     |      0,93 |
| 429     |      0,50 |

Dla wszystkich 9 zdjęć błąd dopasowania znaków tłowych był mniejszy niż 1 piksel.
