# Road Accident MLOps Project Template

This repository provides a clean, modular starting point for MLOps projects focused on road accident data. It follows best practices for project organization and reproducibility. Feel free to adapt it to your needs.


## Project Structure

```sh
├── LICENSE
├── README.md                # Project overview and instructions
├── data/
│   ├── external/            # Third-party data sources
│   ├── interim/             # Intermediate, transformed data
│   ├── processed/           # Final datasets for modeling
│   └── raw/                 # Original, immutable data dumps
├── logs/                    # Training and prediction logs
├── models/                  # Trained models, predictions, summaries
├── notebooks/               # Jupyter notebooks (e.g., 1.0-ldj-initial-data-exploration.ipynb)
├── references/              # Data dictionaries, manuals, and documentation
├── reports/
│   └── figures/             # Generated graphics and figures
├── requirements.txt         # Python dependencies
├── setup.py                 # Project installation script
├── pyproject.toml           # Build system configuration
├── src/                     # Source code
│   ├── __init__.py
│   ├── config/              # Model and training configuration files
│   ├── data/                # Data loading and processing scripts
│   │   ├── check_structure.py
│   │   ├── import_raw_data.py
│   │   └── make_dataset.py
│   ├── features/            # Feature engineering scripts
│   │   └── build_features.py
│   ├── models/              # Model training and prediction scripts
│   │   ├── train_model.py
│   │   ├── predict_model.py
│   │   └── test_features.json
│   └── visualization/       # Visualization scripts
│       └── visualize.py
```


## Getting Started

### 1. Set Up a Virtual Environment

We used `uv` for environment management.

Make sur you install `uv` if not already done.

```bash
uv venv
uv sync
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```
> Note: You may see a warning related to `setup.py`. This does not affect the installation.

### 3. Import Raw Data

Run the script to import the four datasets:

```bash
python src/data/import_raw_data.py
```

> The script will prompt you to create a new folder if needed.

### 4. Prepare the Dataset

Process the raw data into a preprocessed format:

```bash
python src/data/make_dataset.py
```
- Input: `./data/raw`
- Output: `./data/preprocessed`

### 5. Train the Model

Train and serialize the model:

```bash
python src/models/train_model.py
```

### 6. Make Predictions

You can predict using a JSON file (example provided):

```bash
python src/models/predict_model.py src/models/test_features.json
```

Or, if you do not specify a JSON file, the script will prompt you to enter features manually.


## Conventions

- **Run all scripts from the project root** using relative paths as shown above.
- **Notebooks** should follow the naming convention: `<number>-<initials>-<description>.ipynb` (e.g., `1.0-ldj-initial-data-exploration.ipynb`).

---

## References

- Project structure inspired by [cookiecutter data science](https://drivendata.github.io/cookiecutter-data-science/).

---

<small>Adapt and extend as needed for your specific use case.</small>
