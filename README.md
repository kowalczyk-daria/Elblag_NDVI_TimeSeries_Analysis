# Analiza zmian pokrycia terenu Elbląga (2015–2025)
Projekt teledetekcyjny realizowany przy użyciu danych satelitarnych Sentinel-2

## Opis projektu
Projekt służy do oceny zmian w strukturze zazielenienia miasta Elbląg w ostatniej dekadzie. Wykorzystuje wskaźnik NDVI (Normalized Difference Vegetation Index) do identyfikacji powierzchni biologicznie czynnych.

Głównym celem jest przetworzenie wieloczasowych danych rastrowych i wektorowych w celu dostarczenia obiektywnych statystyk środowiskowych dla planowania przestrzennego.

## Wykorzystane technologie

**Język:** Python 3.x

**Analiza wektorowa:** GeoPandas, Shapely

**Przetwarzanie rastrowe:** Rasterio, NumPy

**Akwizycja danych:** Requests (OpenStreetMap Nominatim API)

**Wizualizacja:** Matplotlib, Pandas (analiza trendu)

## Kluczowe funkcjonalności
- Automatyczne pobieranie aktualnych granic administracyjnych Elbląga z bazy OpenStreetMap
- Reprojekcja (CRS alignment) danych wektorowych do układu odniesienia zdjęć satelitarnych
- Przycinanie rastrów do granic poligonu miasta
- Obliczanie wskaźnika NDVI dla kanałów Red (B04) i NIR (B08)
- Wykorzystanie regresji liniowej (metoda najmniejszych kwadratów) do określenia dynamiki zmian zazielenienia w czasie
- Zapis wyników do standardu branżowego GeoTIFF, gotowego do dalszej pracy w profesjonalnym oprogramowaniu (QGIS/ArcGIS).


## Struktura repozytorium

```text
├── data/
│   ├── 2015_B04.tiff
│   ├── 2015_B08.tiff
│   ├── ...
│   ├── 2025_B04.tiff
│   ├── 2025_B08.tiff
├── Elblag_NDVI_TimeSeries_Analysis.ipynb
├── Elblag_NDVI_2025.tif
└── README.md
```
## Wnioski z analizy

Analiza wykazała względną stabilność terenów zielonych (wahania do ~3.5%) w badanym okresie z lekkim trendem wzrostowym wynoszącym 0.16 punktów procentowych rocznie.
