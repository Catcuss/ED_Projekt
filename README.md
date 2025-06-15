# ED_Projekt

**Projekt zaliczeniowy na przedmiot Eksploracja Danych**  
**Politechnika Poznańska – Wydział Informatyki i Telekomunikacji**

## Temat pracy  
**Analiza skupień państw i narodów w kontekście gospodarczo-politycznym**  

## Autorzy  
- **Maria Nowicka** (151851)  
- **Zuzanna Tabisz** (151561)  

## Opis projektu

Celem projektu była analiza skupień (klasteryzacja) państw na podstawie danych społeczno-ekonomicznych, zdrowotnych, edukacyjnych i politycznych, pochodzących z bazy **World Development Indicators** (Bank Światowy). Zastosowano klasyczne metody eksploracji danych w celu identyfikacji naturalnych grup krajów o zbliżonych cechach.

Analiza miała charakter eksperymentalny i została przeprowadzona przy użyciu trzech metod klasteryzacji:
- **K-means** (metoda bazowa),
- **DBSCAN**,
- **analiza hierarchiczna**.

Do przetwarzania danych zastosowano m.in.:
- oczyszczanie danych (usuwanie braków, standaryzacja),
- redukcję wymiarowości (t-SNE, TruncatedSVD),
- dyskretyzację i normalizację danych (KBinsDiscretizer, MinMaxScaler).

Wyniki analizy były wizualizowane przy użyciu interaktywnych wykresów i oceniane za pomocą metryk takich jak:
- **silhouette score**,
- **odległość wewnątrz- i międzyklastrowa**,
- **znormalizowana informacja wzajemna (NMI)**.

## Źródła danych

Dane pochodzą z bazy **World Bank – World Development Indicators** (https://databank.worldbank.org/source/world-development-indicators).  

W analizie uwzględniono dane z 2022 roku obejmujące 217 krajów i ponad 1600 wskaźników, w podziale na 8 kategorii:
- Polityka gospodarcza i zadłużenie,
- Edukacja,
- Środowisko,
- Sektor finansowy,
- Zdrowie,
- Sektor prywatny i handel,
- Sektor publiczny,
- Ochrona socjalna i rynek pracy.

## Przykładowy zbiór danych

W katalogu `data/` znajdują się tematyczne pliki CSV z przykładowymi danymi. Każdy plik odpowiada jednej dziedzinie analizy:

- `wb_econ.csv` – dane gospodarcze,
- `wb_edu.csv` – dane edukacyjne,
- `wb_env.csv` – dane środowiskowe,
- `wb_fin.csv` – dane finansowe,
- `wb_health.csv` – dane zdrowotne,
- `wb_private.csv` – sektor prywatny i handel,
- `wb_public.csv` – sektor publiczny,
- `wb_soc.csv` – ochrona socjalna i rynek pracy,
- `index.csv` – metadane lub plik indeksujący kolumny i źródła danych.

## Wymagania

Projekt został zaimplementowany w języku Python. Do uruchomienia wymagane są następujące biblioteki :
- numpy
- pandas
- scikit-learn
- matplotlib
- plotly
- scipy

## Plik z projekterm

W katalogu 'notebooks/' znajduje się plik ED_Projekt.ipynb w którym znajduje się pipeline przetwarzania danych, redukcji wymiarowości oraz klasteryzacji.

## Wyniki
Rezultat analizy to :
- interaktywne wizualizacje klastrów,
- wykresy t-SNE i SVD,
- statystyki jakości klasteryzacji
