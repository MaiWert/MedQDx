# MedQDx: EDA & Baseline

Welcome to the **MedQDx** project! This repository contains exploratory data analysis (EDA), baseline case generation, and evaluation for symptom‑disease prediction.

## 📚 Dataset

We use the [Symptom‑Disease Prediction Dataset (SDPD)](https://data.mendeley.com/datasets/dv5z3v2xyd/1)
The Symptom-Disease Prediction Dataset (SDPD) is a comprehensive collection of structured data linking symptoms to various diseases, meticulously curated to facilitate research and development in predictive healthcare analytics.
This dataset provides a comprehensive collection of disease names and associated symptoms, encoded in a one-hot manner.
Each row in the dataset represents a single instance.
Each symptom can be 0/1 for each disease, where:
1 indicates the symptom is relevant to the disease
0 implies no relevance

* Contains patient records mapping sets of symptoms to diagnoses (prognoses).
* Original CSV file: `symbipredict_2022.csv`.
* Size: 4961 rows | 132 symptoms | 41 unique diseases

## 💡 Project Overview

The Jupyter notebook `MedQDx__EDA_and_Baseline.ipynb` covers:

1. **Exploratory Data Analysis**

   * Inspecting duplicates and dropping identical rows.
   * Removing single‑value symptom columns.
   * Visualizing disease‑symptom distributions.
   * Filtering cases with at least 5 symptoms.

2. **Baseline Case Generation**

   * A function `call_gpt4o_mini(...)` uses the OpenAI (Azure OpenAI) API to generate three versions of a clinical vignette:

     * **100% Case:** includes all original symptoms.
     * **80% Case:** includes \~80% of symptoms.
     * **50% Case:** includes \~50% of symptoms.
   * Saves generated cases for a random sample of 100 diseases to `benchmark_cases100.csv`.

3. **Evaluation via Jaccard Similarity**

   * Extracts the symptoms list from the generated text.
   * Computes the overlap between the original symptoms and each case via Jaccard similarity.
   * Reports average overlap and the percentage of cases respecting the expected confidence gradient (`100% ≥ 80% ≥ 50%`).

## 🚀 Getting Started

### 1. Clone this repository

```bash
git clone https://github.com/MaiWert/MedQDx.git
cd MedQDx
```

### 2. Set up a Python environment

```bash
python3 -m venv venv
source venv/bin/activate      # on macOS/Linux
venv\Scripts\activate       # on Windows
pip install --upgrade pip
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

> **Note:** If `requirements.txt` is not present, install manually:
>
> ```bash
> pip install pandas numpy matplotlib seaborn scikit-learn tqdm transformers openai azure-openai requests
> ```

### 4. Configure API credentials

Set the following environment variables to enable case generation:

```bash
export MedQDx_ENDPOINT="https://<your‑azure‑endpoint>"
export MedQDx_API_key="<your‑api‑key>"
export MedQDx_api_version="2024-12-01-preview"
export MedQDx_deployment="gpt-4o-mini"
```

### 5. Run the notebook

Launch Jupyter Lab or Notebook and execute all cells:

```bash
jupyter notebook MedQDx__EDA_and_Baseline.ipynb
```

## 📝 Outputs

* **EDA results:** displayed inline charts and tables in the notebook.
* **Generated cases:** `benchmark_cases100.csv` containing 100 sets of 100%, 80%, and 50% cases.
* **Evaluation summary:** Jaccard similarity statistics printed in the notebook.
