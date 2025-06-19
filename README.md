# ED_Projekt

**Projekt zaliczeniowy na przedmiot Eksploracja Danych**  
Politechnika Poznańska – Wydział Informatyki i Telekomunikacji  
Rok I, semestr 1, studia II stopnia

## Temat pracy

**Analiza skupień państw i narodów w kontekście gospodarczo-politycznym**

## Autorzy

- Maria Nowicka (151851)  
- Zuzanna Tabisz (151561)

## Opis projektu

Celem projektu jest analiza skupień (klasteryzacja) państw na podstawie danych społeczno-ekonomicznych, zdrowotnych, edukacyjnych i politycznych z bazy *World Development Indicators* (Bank Światowy) za rok 2022. Projekt ma charakter eksperymentalny i wykorzystuje klasyczne metody eksploracji danych do identyfikacji naturalnych grup krajów o podobnych cechach.

### Zastosowane metody klasteryzacji:

- **K-means** – algorytm partycyjny minimalizujący wariancję wewnątrz klastrów  
- **DBSCAN** – algorytm oparty na gęstości, grupujący punkty blisko siebie położone  
- **Analiza hierarchiczna** – buduje hierarchię klastrów poprzez łączenie lub dzielenie grup

### Przetwarzanie danych obejmuje:

- Oczyszczanie (usuwanie braków, imputacja)  
- Standaryzację i normalizację (np. MinMaxScaler)  
- Redukcję wymiarowości (t-SNE, TruncatedSVD)  
- Dyskretyzację (KBinsDiscretizer)

### Ewaluacja metod:

- **Silhouette Score** – ocena spójności i separacji klastrów  
- **Odległość wewnątrz- i międzyklastrowa** – miary zwartości i rozróżnialności  
- **Znormalizowana informacja wzajemna (NMI)** – porównanie zgodności między metodami i zbiorami  
- **Noise Ratio** – procent punktów nieprzypisanych do klastrów (dla DBSCAN)

## Źródła danych

Dane pochodzą z bazy **World Bank – World Development Indicators** i obejmują 217 krajów oraz ponad 1600 wskaźników podzielonych na osiem kategorii:

- Polityka gospodarcza i zadłużenie  
- Edukacja  
- Środowisko  
- Sektor finansowy  
- Zdrowie  
- Sektor prywatny i handel  
- Sektor publiczny  
- Ochrona socjalna i rynek pracy

Pliki CSV znajdują się w katalogu `data/`:

- `wb_econ.csv` – Dane gospodarcze  
- `wb_edu.csv` – Dane edukacyjne  
- `wb_env.csv` – Dane środowiskowe  
- `wb_fin.csv` – Dane finansowe  
- `wb_health.csv` – Dane zdrowotne  
- `wb_private.csv` – Sektor prywatny i handel  
- `wb_public.csv` – Sektor publiczny  
- `wb_soc.csv` – Ochrona socjalna i rynek pracy  
- `index.csv` – Plik indeksujący kolumny i źródła danych

## Wymagania

Projekt został zaimplementowany w języku **Python**. Wymagane biblioteki:

- `numpy`  
- `pandas`  
- `scikit-learn`  
- `matplotlib`  
- `plotly`  
- `scipy`

Instalacja:

```bash
pip install numpy pandas scikit-learn matplotlib plotly scipy
```

## Struktura projektu

Notebook `notebooks/ED_Projekt.ipynb` zawiera pełny pipeline analizy:

### Przetwarzanie danych

- Porównanie zbiorów przed i po imputacji (liczba wierszy/kolumn, procent braków, wariancja, unikalne wartości)  
- Top 5 korelacji dla każdego zbioru po imputacji  
- Analiza wybranych cech (wariancja i unikalność)

### Klasteryzacja

- Implementacja metod: **K-means**, **DBSCAN**, **analiza hierarchiczna**

### Wizualizacje

- Statyczne wykresy (dendrogramy, Silhouette Score, scatter ploty) – zgodne z ograniczeniami GitHub

### Ewaluacja

- Metryki: **Silhouette Score**, **odległości wewnątrz-/międzyklastrowe**, **Noise Ratio**  
- Macierze **NMI** porównujące metody i zbiory danych  
- Listy wybranych cech dla każdego zbioru

---

## Wyniki

Projekt dostarcza:

- Interaktywne wizualizacje klastrów (*statyczne wersje w notebooku*)  
- Wykresy **t-SNE** i **SVD**  
- Statystyki jakości klasteryzacji: *Silhouette Score*, *NMI* itp.  
- Porównanie skuteczności zastosowanych metod klasteryzacji

Szczegółowe wnioski znajdują się w dokumentacji.

---

## Dokumentacja projektu

W katalogu `docs/` znajdują się:
- **Sprawozdanie w pdf** – zawiera pełny opis metodologii, szczegółowe wyniki analiz, wizualizacje oraz porównanie skuteczności poszczególnych metod klasteryzacji.
- **Prezentacja** – skrótowy przegląd projektu, przygotowany na potrzeby prezentacji zaliczeniowej.

