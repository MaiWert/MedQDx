# MedQDx Evaluation

This section contains a Jupyter/Colab notebook (`MedQDx_Evaluation.ipynb`) to evaluate the diagnostic performance of Azure OpenAI's GPT‑4.1 model on a medical diagnosis benchmark. It simulates clinical cases with varying levels of symptom completeness (100%, 80%, and 50%) and computes zero‑shot diagnostic accuracy using string similarity measures.

## 🔍 Features

* **Dependency setup** via `pip` for OpenAI, Transformers, Azure Core, and more
* **Data ingestion**: Loads `MedQDx_benchmark.csv` containing true labels and case texts
* **Similarity metrics**: Uses Python's `difflib` and `sklearn` to compute:

  * Mean of maximum similarity per case
  * Mean similarity across three rounds
* **Azure OpenAI integration**:

  * Connects to GPT‑4.1 deployment via Azure OpenAI SDK
  * Defines helper functions:

    * `get_diagnosis(case_text)` – sends prompt to model and retrieves prediction
    * `is_similar(pred, true, threshold=0.6)` – flags correct diagnosis by similarity threshold
* **Evaluation loop**: Processes case texts at 100%, 80%, and 50% symptom completeness
* **Results display**: Outputs summary DataFrame and detailed per‑case similarity scores

---

## ⚙️ Requirements

* Python 3.7 or higher
* Packages:

  * `openai`
  * `transformers`
  * `accelerate`
  * `bitsandbytes`
  * `azure-core`
  * `pandas`
  * `tqdm`
  * `torch`
  * `scikit-learn`

---

## 🚀 Installation

1. Clone this repo:

   ```bash
   git clone https://github.com/<your-username>/MedQDx_Evaluation.git
   cd MedQDx_Evaluation
   ```

2. Install dependencies:

   ```bash
   pip install openai transformers accelerate bitsandbytes azure-core pandas tqdm torch scikit-learn
   ```

3. (Optional) If using Colab, mount Google Drive:

   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```

---

## 🛠️ Usage

1. **Prepare data**: Place `MedQDx_benchmark.csv` in the notebook directory or update the file path in the notebook.
2. **Configure credentials**:

   ```python
   AZURE_ENDPOINT = "<your_azure_endpoint>"
   AZURE_API_KEY  = "<your_azure_api_key>"
   AZURE_API_VERSION = "2024-12-01-preview"
   AZURE_DEPLOYMENT_NAME = "gpt-4.1"
   ```
3. **Run the notebook**:

   * In Jupyter Lab/Notebook or
   * In Google Colab

Cells execute in order:

1. Install dependencies
2. Import libraries
3. Load data
4. Compute the similarity summary
5. Set up Azure OpenAI client & define helper functions
6. Run diagnosis & evaluation loop
7. Display detailed results

---

## 📝 Notebook Structure

| Section                    | Description                                    |
| -------------------------- | ---------------------------------------------- |
| **Dependencies & Imports** | Installs packages & imports required libraries |
| **Data Loading**           | Reads benchmark CSV into pandas DataFrame      |
| **Similarity Summary**     | Calculates mean and round‑wise similarity      |
| **Azure OpenAI Setup**     | Configures client & defines `get_diagnosis`    |
| **Evaluation Loop**        | Generates predictions and computes accuracy    |
| **Results**                | Displays summary DataFrame and prints details  |

---

## 📊 Results

The notebook outputs:

* **Mean of max similarity** across all cases
* **Mean similarity** for each of the three symptom completeness levels
* **Zero‑shot diagnostic accuracy** (similarity ≥ 0.6) for 100%, 80%, and 50% cases
