# 🩺 MedQDx: Diagnose Like a Doctor 🩺

MedQDx is a cutting-edge benchmark designed to evaluate large language models (LLMs) in **interactive**, **uncertain** diagnostic scenarios. By simulating physician–patient dialogues with **partial clinical information**, MedQDx measures an LLM’s ability to:

* 🔎 Ask targeted questions
* 🔄 Adapt its line of inquiry
* 🎯 Arrive at accurate diagnoses under uncertainty

![image](https://github.com/user-attachments/assets/0a458462-814e-4504-8a66-ed0afd5f4a19)

## 📖 Table of Contents

1. [💡 Introduction](#💡-introduction)
2. [🗂️ Project Structure](#🗂️-project-structure)
3. [⚙️ Getting Started](#⚙️-getting-started)
4. [📚 Submodule Overviews](#📚-submodule-overviews)

   * [🧪 EDA & Baseline](#🧪-eda--baseline)
   * [🎬 Benchmark Creation](#🎬-benchmark-creation)
   * [📊 Evaluation](#📊-evaluation)
5. [📈 Presentation](#📈-presentation)
6. [🤝 Contributing](#🤝-contributing)



## 💡 Introduction

Patients rarely present a complete clinical picture initially. Physicians must conduct **dynamic dialogues**, asking the right questions to uncover missing information and ensure **high-quality diagnosis**. MedQDx addresses this gap by simulating partial patient cases (100%, 80%, 50% symptom coverage) and evaluating an LLM’s:

* 🏅 **Zero-Shot Diagnostic Accuracy (ZDA)**
* 📏 **Mean Diagnostic Similarity**

By requiring multi-turn doctor–patient interactions, we push AI from passive responders to active clinical reasoning partners.


## 🗂️ Project Structure

```bash
MedQDx/                                  # 🏠 Root folder
├── EDA and Baseline/                     # 🧪 Data exploration & baseline case generation
│   ├── 📄 EDA & Baseline README.md
│   ├──  MedQDx__EDA_and_Baseline.ipynb
│   └──  Patient cases.csv
├── Benchmark Creation/                   # 🎬 Simulate doc–patient dialogues
│   ├── 📄 Benchmark Creation README.md
│   ├──  MedQDx_Benchmark_Creation.ipynb
│   └──  MedQDx_Benchmark.csv
├── Benchmark Evaluation/                           # 📊 Diagnostic performance evaluation
│   ├── 📄 Evaluation README.md
│   └──  MedQDx_Evaluation.ipynb
├── Presentations/
│   ├──  MedQDx - Final Presentation.pdf
│   ├──  MedQDx - Interim Presentation.pdf
│   └──  MedQDx - Project proposal.pdf
└── 📘 README.md                           # ← You are here!
```


## ⚙️ Getting Started

1. **Clone the repository**

   ```bash
   git clone https://github.com/MaiWert/MedQDx.git
   cd MedQDx
   ```
2. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```
3. **Configure credentials**

   ```bash
   export MedQDx_ENDPOINT="https://<your-azure-endpoint>"
   export MedQDx_API_KEY="<your-api-key>"
   export MedQDx_API_VERSION="2024-12-01-preview"
   ```
4. **Launch notebooks**

   * 🧪 `EDA & Baseline/MedQDx__EDA_and_Baseline.ipynb`
   * 🎬 `Benchmark Creation/MedQDx_Benchmark_Creation.ipynb`
   * 📊 `Evaluation/MedQDx_Evaluation.ipynb`



## 📚 Submodule Overviews

### 🧪 EDA & Baseline

Dive into the Symptom–Disease Prediction Dataset (SDPD) with cleaning, exploratory analysis, and baseline patient case generation. Covers 100%, 80%, and 50% symptom reveals with Jaccard analysis.

> 🔗 [Explore](./EDA%20and%20Baseline/EDA%20%26%20Baseline%20README.md)

### 🎬 Benchmark Creation

Simulate doctor–patient dialogues using different LLM personas. Collect questions, answers, and diagnoses for each partial case and export detailed conversation logs.

> 🔗 [Simulate](./Benchmark%20Creation/Benchmark%20Creation%20README.md)

### 📊 Evaluation

Assess the AI diagnostician’s performance by calculating ZDA, similarity metrics, and visualizing results across symptom completeness tiers.

> 🔗 [Evaluate](./Evaluation/Evaluation%20README.md)


## 🤝 Contributing

Your ideas make MedQDx better! Follow these steps to contribute:

1. 🔀 Fork the repo
2. 🌱 Create a branch: `git checkout -b feature/your-awesome-idea`
3. 💾 Commit: `git commit -m "Add amazing feature"`
4. 🔄 Push & PR: `git push origin feature/your-awesome-idea`


---

*✨ MedQDx © 2025 Mai Werthaim & Maya Kimhi*
