# MedQDx: Benchmark Creation

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE) [![Python Version](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](#)

An interactive diagnostic benchmark workflow using two Large Language Models (LLMs): a **Doctor LLM** (e.g., GPT-4.1 via Azure OpenAI) and a **Patient LLM** (e.g., GPT-4o-mini). This notebook simulates clinical dialogues, measures diagnostic accuracy, and compares performance across varying symptom coverage levels.

---

## ✨ Features

* ✅ **Doctor–Patient Simulation**: Generate doctor questions and patient responses in a loop.
* ✅ **Multi‑Coverage Cases**: Evaluate at **100%**, **80%**, and **50%** symptom coverage.
* ✅ **Similarity Scoring**: Compute embedding‑based cosine similarity for diagnosis evaluation.
* ✅ **CSV Export**: Save detailed predictions, scores, and accuracy metrics.
* ✅ **Colab‑Ready**: Includes Google Drive mounting snippet for easy data access.

---

## 🚀 Quick Start

1. **Clone the repo**

   ```bash
   git clone https://github.com/<your-username>/MedQDx-Benchmark.git
   cd MedQDx-Benchmark
   ```
2. **Open in Colab or Jupyter**

   * **Colab**: Click “Open in Colab” badge (add badge link if available).
   * **Local**: Launch:

     ```bash
     jupyter notebook MedQDx_Benchmark_Creation.ipynb
     ```
3. **Run all cells** to simulate dialogues and view results.

---

## ⚙️ Prerequisites

* **Python**: 3.8 or higher
* **Azure/OpenAI**: Endpoint & API key for GPT-4.1 or equivalent
* **Patient LLM**: Access to GPT-4o-mini or similar
* **Data**: `patient_cases.csv` with columns:

  * `prognosis`
  * `Full_Case`
  * `80% Case`
  * `50% Case`

---

## 🛠️ Installation & Configuration

1. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   # or in Colab:
   !pip install openai azure-ai-inference pandas
   ```

2. **Set credentials** (in notebook cells):

   ```python
   endpoint    = "<YOUR_AZURE_ENDPOINT>"
   api_key     = "<YOUR_AZURE_API_KEY>"
   api_version = "2024-12-01-preview"
   ```

3. **(Optional) Mount Google Drive**

   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```

4. **Place `patient_cases.csv`** in your working directory or Drive path.

---

## 📖 Notebook Structure

| Section                    | Description                                                     |
| -------------------------- | --------------------------------------------------------------- |
| **Setup & Imports**        | Install packages, import libs, mount drive                      |
| **Doctor LLM Prompts**     | Build/send prompts for doctor questions & final diagnosis       |
| **Patient LLM Prompts**    | Build/send prompts for patient answers                          |
| **Similarity Calculation** | Compute embedding similarity between predicted & true diagnoses |
| **Benchmark Loop**         | Iterate cases, simulate dialogues, collect metrics              |
| **Export & Analysis**      | Save to CSV & display summary (Zero‑Shot Diagnostic Accuracy)   |

---

## ▶️ Usage

1. **Execute** each cell in order.
2. **Monitor** output for per-case logs and similarity scores.
3. **Review** summary metrics for 50%, 80%, and 100% scenarios.

---

## 📂 Output

* **`results.csv`**: Raw data with predictions, similarity scores, and correctness flags.
* **Summary table**: Displayed in‑notebook (e.g., ZDA for each coverage level).
