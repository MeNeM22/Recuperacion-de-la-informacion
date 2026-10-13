
<h1 align="center">🌐 Web Information Retrieval</h1>

<p align="center">
  <strong>Collecting, processing and exporting information from APIs, web pages and RSS feeds using Python.</strong>
</p>

<p align="center">
  🎓 Academic team project · Universidad Nacional de Tres de Febrero (UNTREF)
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Requests-2C5BB4?style=for-the-badge&logo=python&logoColor=white" alt="Requests" />
  <img src="https://img.shields.io/badge/BeautifulSoup-4B8BBE?style=for-the-badge&logo=python&logoColor=white" alt="BeautifulSoup" />
  <img src="https://img.shields.io/badge/RSS-FFA500?style=for-the-badge&logo=rss&logoColor=white" alt="RSS" />
  <img src="https://img.shields.io/badge/Pytest-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white" alt="Pytest" />
</p>

<hr width="100%">

## 📖 Overview

This Python command-line application brings together **three approaches to information retrieval**:

- **REST API consumption:** Queries OpenAlex for scientific publications and extracts structured metadata.
- **Web scraping:** Collects information about trade fairs and events from EventsEye, Nferias and 10Times.
- **RSS processing:** Reads news feeds from BBC and El País, identifies countries mentioned and stores the results.

The application provides an interactive terminal menu and exports the collected information to **CSV files** for later inspection.

## ✨ Features

| Module | Functionality | Output |
|---|---|---|
| OpenAlex | Search publications, extract authors, dates, topics, keywords, institutions and abstracts | `data/articulos.csv` |
| Web Scraping | Extract event names, dates, locations, descriptions, sectors and contact information | `data/eventos.csv` |
| RSS | Parse news titles, summaries, dates and related countries | `data/noticias.csv` |
| CLI | Execute queries and inspect stored information | Terminal |

### 🔍 Technical Highlight: Abstract Reconstruction

OpenAlex represents some publication abstracts using an **inverted index**, where each word is associated with its positions in the original text.

The `extraer_resumen()` function reconstructs the abstract by placing tokens at their corresponding positions.

```python
inverted_index = {
    "data": [0],
    "engineering": [1]
}

# Reconstructed abstract:
# "data engineering"
```

This demonstrates the practical use of **dictionaries, lists, and positional indexing**.

## 🏗️ Project Structure

```text
.
├── main.py
├── requirements.txt
├── src/
│   ├── api/
│   │   └── api_open_alex.py
│   ├── scraping/
│   │   ├── eventsEyeScrap.py
│   │   ├── nferiasScrap.py
│   │   ├── tenTimesScrap.py
│   │   └── guardarEventos.py
│   ├── rss/
│   │   └── lector.py
│   ├── interfaz/
│   │   └── menu.py
│   └── utils/
│       └── utilidades.py
├── data/
│   ├── articulos.csv
│   ├── eventos.csv
│   └── noticias.csv
├── tests/
├── docs/
│   ├── notebook/
│   └── presentacion/
└── LICENSE
```

## 🚀 Getting Started

### Prerequisites

- Python 3.10+ recommended
- pip
- Git

### 1. Clone the Repository

```bash
git clone https://github.com/MeNeM22/Recuperacion-de-la-informacion.git
cd Recuperacion-de-la-informacion
```

### 2. Create a Virtual Environment

```bash
python -m venv .venv
```

**Linux / macOS:**

```bash
source .venv/bin/activate
```

**Windows PowerShell:**

```powershell
.venv\Scripts\Activate.ps1
```

### 3. Install Dependencies

```bash
python -m pip install -r requirements.txt
```

### 4. Run the Application

```bash
python main.py
```

The interactive menu allows users to:

1. Query scientific articles from OpenAlex.
2. Extract trade fair and event information.
3. Retrieve news from RSS feeds.
4. View previously generated CSV files.
5. Access project information.

Live operations depend on external service availability and website structure.

## 📂 Example Data

The repository includes CSV datasets generated during development.

| Dataset | Records |
|---|---:|
| Scientific articles | 50 |
| Events and trade fairs | 18 |
| RSS news | 171 |

These figures describe the included dataset snapshot, not live results.

## 🧪 Testing

The project uses **pytest** for automated testing.

Four new offline unit tests cover:

- OpenAlex requests using HTTP mocks.
- Network error handling.
- Metadata extraction and abstract reconstruction.
- CSV persistence using temporary files.

Run the new tests with:

```bash
python -m pytest -q tests/test_openalex_unit.py
```

The older integration tests still require improvements because some depend on live services or modify existing CSV files. Avoid running the full suite against your only copy of the data.

## 🛠️ Current Limitations and Improvements

- Improve RSS duplicate detection using stable identifiers.
- Increase scraper resilience when external HTML structures change.
- Replace legacy placeholder tests with functional unit tests.
- Isolate filesystem and network operations during testing.
- Update older planning documents to distinguish proposed features from implemented ones.

## 📚 Documentation

The repository includes additional technical materials:

- [Jupyter Notebook Report](docs/notebook/informe_tp.ipynb)
- [Project Structure](ESTRUCTURA_PROYECTO.md)
- [Automated Tests](tests/)

## 👥 Team and Contributions

This project was developed collaboratively by:

- Agustín Menechino
- Gonzalo Hernández
- Luciano Díaz
- Jazmín Cabral

**Agustín's contribution:** OpenAlex API integration, metadata processing and CSV export.

The scraping, RSS and console modules are part of the wider team project.

## 📄 License

This project is distributed under the [Unlicense](LICENSE).

<hr width="100%">

<h3 align="center">Connect with me</h3>

<p align="center">
  <a href="https://github.com/MeNeM22">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
  </a>
  <a href="https://www.linkedin.com/in/agustin-francisco-menechino-castro-b0362323a/">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
</p>
