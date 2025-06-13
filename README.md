# pte-personal-scrap

A data pipeline project for scraping, transforming, and analyzing personnel data from various ministries.

## Project Structure

```
.
├── .gitignore
├── README.md
├── requirements.txt
├── .devcontainer/
│   ├── devcontainer.json
│   └── Dockerfile
├── data/
│   ├── id_ministerios.xlsx
│   ├── bronze/
│   │   └── id_entidad=.../
│   ├── silver/
│   ├── gold/
│   └── control/
└── src/
    ├── scrap.ipynb
    └── transform.ipynb
```

- **.devcontainer/**: Configuration for development containers (VS Code Remote Containers).
- **data/**: Data storage, organized by processing stage:
  - **bronze/**: Raw scraped data, partitioned by entity.
  - **silver/**: Cleaned and transformed data.
  - **gold/**: Final, analysis-ready datasets.
  - **control/**: Control files or logs for pipeline management.
  - **id_ministerios.xlsx**: Reference file for ministry/entity IDs.
- **src/**: Source code and notebooks for scraping and transforming data.

## Getting Started

### Prerequisites

### Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/your-username/pte-personal-scrap.git
    cd pte-personal-scrap
    ```

2. Set up the docker image:
   ```sh
   docker build -t pte-personal-scrap:latest -f .devcontainer/Dockerfile .
   docker run -dit --name pte-personal-scrap -v "$repopath:/workspace" -w /workspace pte-personal-scrap:latest
   ```


## Usage

- Run the scraping notebook:
    - Open [`src/scrap.ipynb`](src/scrap.ipynb) and execute cells to collect raw data into the `data/bronze/` directory.
- Run the transformation notebook:
    - Open [`src/transform.ipynb`](src/transform.ipynb) and execute cells to process data into `data/silver/` and `data/gold/`.

## Data Flow

1. **Bronze**: Raw data from scraping.
2. **Silver**: Cleaned and normalized data.
3. **Gold**: Aggregated, analysis-ready datasets.
