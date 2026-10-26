# Źródła danych

## Historyczne zdjęcia lotnicze

**Źródło:** swisstopo — LUBIS  
**Data nalotu:** 17 maja 1976  
**Obszar:** Zürich-Kloten / Bülach, Szwajcaria  
**Typ danych:** czarno-białe skany analogowych zdjęć lotniczych

W projekcie wykorzystano blok 9 zdjęć:

- 301, 302, 303
- 378, 379, 380
- 427, 428, 429

Zdjęcia wraz z metadanymi stanowiły podstawowe dane wejściowe do przetwarzania fotogrametrycznego.

Oficjalne źródło:  
https://www.swisstopo.admin.ch/en/application-lubis-viewer

---

## Kalibracja kamery

Do rekonstrukcji orientacji wewnętrznej wykorzystano certyfikat kalibracji kamery **Wild RC10** z obiektywem **Universal Aviogon II nr 3008**.

Parametry użyte podczas konfiguracji kamery zostały opisane osobno w pliku:

`methodology/camera_calibration.md`

---

## SWISSIMAGE

**Dostawca:** swisstopo  
**Produkt:** SWISSIMAGE  
**Rozdzielczość wykorzystana w projekcie:** 2 m  
**CRS:** CH1903+ / LV95 — EPSG:2056

Kafle zostały połączone w QGIS do pliku:

`SWISSIMAGE_2m_merged.tif`

Dane wykorzystano jako:

- źródło referencyjne podczas zbierania GCP,
- współczesny obraz do porównania z ortomozaiką z 1976 roku.

Oficjalne źródło:  
https://www.swisstopo.admin.ch/en/orthoimage-swissimage-10

---

## swissALTI3D

**Dostawca:** swisstopo  
**Produkt:** swissALTI3D  
**Typ:** numeryczny model terenu DTM  
**Rozdzielczość:** 2 m  
**CRS:** CH1903+ / LV95 — EPSG:2056

176 kafli połączono w QGIS do pliku:

`swissALTI3D_merged.tif`

Model wykorzystano jako referencyjne dane wysokościowe podczas przetwarzania fotogrametrycznego.

Oficjalne źródło:  
https://www.swisstopo.admin.ch/en/height-model-swissalti3d

---

## Oprogramowanie

### CATALYST Professional

**Wersja:** 3.4.0  
**Build:** 2026-06-12

Wykorzystane moduły:

- Historical Airphoto Processing (HAP),
- OrthoEngine,
- Mosaic Tool,
- Focus.

Główna dokumentacja workflow:  
https://catalyst.earth/tutorial/historical-airphoto-processing-hap/

### QGIS

QGIS wykorzystano pomocniczo do:

- łączenia kafli danych referencyjnych,
- kontroli GeoTIFF,
- eksportów,
- przycinania rastrów,
- porównania historycznego i współczesnego,
- przygotowania danych do interaktywnej prezentacji.

---

## Układ współrzędnych

Finalne produkty zapisano w:

**CH1903+ / LV95 — EPSG:2056**

Wysokości przetwarzano w metrach z odniesieniem do średniego poziomu morza.

---

## Dane przechowywane poza repozytorium

Repozytorium nie zawiera pełnych danych źródłowych ze względu na ich rozmiar oraz warunki udostępniania.

Nie są przechowywane między innymi:

- oryginalne skany LUBIS,
- pełny zestaw SWISSIMAGE,
- pełny zestaw swissALTI3D,
- pliki tymczasowe CATALYST,
- obrazy epipolarne.

Repozytorium zawiera dokumentację źródeł oraz wybrane produkty końcowe projektu.
