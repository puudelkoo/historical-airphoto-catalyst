# Workflow przetwarzania

## 1. Przygotowanie danych

Do projektu wybrano blok 3 × 3 obejmujący 9 historycznych zdjęć lotniczych z 17 maja 1976 roku.

Dodatkowo przygotowano:

- SWISSIMAGE 2 m jako współczesne dane referencyjne,
- swissALTI3D 2 m jako referencyjny DTM,
- certyfikat kalibracji kamery Wild RC10.

Finalny układ współrzędnych:

**CH1903+ / LV95 — EPSG:2056**

---

## 2. HAP Ingest

Zdjęcia oraz metadane zostały zaimportowane przy użyciu modułu Historical Airphoto Processing.

CATALYST utworzył:

- projekt fotogrametryczny,
- informacje o orientacji zewnętrznej,
- trzy flightlines obejmujące po trzy zdjęcia.

---

## 3. Orientacja wewnętrzna

Dla wszystkich zdjęć zebrano cztery narożne znaki tłowe.

Po konfiguracji kamery wykorzystano automatyczną detekcję `AUTOFID`.

Wszystkie zdjęcia uzyskały błąd znaków tłowych poniżej 1 px.

---

## 4. Nominalne georeferencjonowanie

Na podstawie metadanych nalotu i orientacji zdjęć wykonano nominalne georeferencjonowanie całego bloku.

Etap ten pozwolił przygotować zdjęcia do dalszego wyrównania na podstawie danych referencyjnych.

---

## 5. Ground Control Points

Punkty GCP zbierano na podstawie współczesnej ortofotomapy SWISSIMAGE.

Wybierano przede wszystkim stabilne obiekty możliwe do identyfikacji zarówno na zdjęciach z 1976 roku, jak i na danych współczesnych, np.:

- skrzyżowania,
- elementy infrastruktury drogowej,
- trwałe obiekty terenowe.

Początkowo zebrano 12 punktów ręcznie.

---

## 6. Tie Points

Tie points wygenerowano automatycznie.

Dla czarno-białych zdjęć wykorzystano kanał `1`.

Po automatycznym dopasowaniu punkty zapewniły połączenia pomiędzy zdjęciami w całym bloku.

---

## 7. Alignment

Wykonano trzy etapy wyrównania:

1. **Coarse Alignment — stage1**
2. **Fine Alignment — stage2**
3. **Fine Alignment — stage3**

Podczas QA usunięto najbardziej odstające automatyczne GCP.

Po wyrównaniu uzyskano stabilną geometrię bloku i niskie błędy tie points.

---

## 8. Rekonstrukcja DSM

Na podstawie projektu `stage3Auto.prj` utworzono 6 optymalnych par stereo.

Dla każdej pary wygenerowano obrazy epipolarne.

DSM wygenerowano metodą:

**SGM — Semi-Global Matching**

Parametry końcowego modelu:

- rozdzielczość: 1 × 1 m,
- odniesienie wysokości: Mean Sea Level,
- połączenie wyników: Merge.

Wynik:

`DSM_1976.tif`

---

## 9. Ortorektyfikacja

Wszystkie 9 zdjęć zostało ortorektyfikowanych przy użyciu wygenerowanego DSM.

Zastosowano:

- sampling interval: 1,
- resampling: Cubic,
- automatic edge clip: 5%.

Wyniki zapisano jako pojedyncze pliki `.pix`.

---

## 10. Mozaikowanie

Dziewięć ortoobrazów połączono w Mosaic Tool.

Zastosowano:

- automatyczne cutlines,
- metodę `Minimum squared difference`,
- color balancing `Bundle`,
- blend width: 10 px.

Wynik:

`historical_orthomosaic_1976.tif`

---

## 11. Kontrola jakości

Finalną mozaikę sprawdzono wizualnie przy większych skalach.

Kontrolowano między innymi:

- ciągłość dróg,
- krawędzie budynków,
- pasy startowe lotniska,
- przejścia pomiędzy zdjęciami,
- ghosting,
- lokalne przesunięcia,
- różnice jasności.

Nie stwierdzono istotnych błędów uniemożliwiających wykorzystanie finalnej ortomozaiki.

---

## 12. Porównanie 1976 — współcześnie

Historyczna ortomozaika została porównana z aktualnym SWISSIMAGE.

Szczególnie czytelne zmiany widoczne są w rejonie lotniska Zürich-Kloten:

- rozwój infrastruktury terminalowej,
- rozbudowa dróg kołowania i płyt postojowych,
- rozwój sieci drogowej,
- wzrost zabudowy,
- zmiany użytkowania terenu.

Na potrzeby prezentacji przygotowano również lokalny interaktywny viewer umożliwiający:

- zmianę przezroczystości warstw,
- zoom,
- przesuwanie obrazu,
- bezpośrednie porównanie 1976 roku ze stanem współczesnym.
