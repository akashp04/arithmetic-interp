# arithmetic-interp

## Overview

This repository provides evaluation scripts and results for **Arithmetic Length Generalization Dataset (ALGD)**, a benchmark designed to test the arithmetic reasoning and length generalization capabilities of large language models (LLMs). The ALGD dataset evaluates models on arithmetic tasks such as addition, subtraction, multiplication, division, and modulus operations across varying numerical complexities (1-digit to 7-digit numbers).

The ALGD dataset is hosted on Hugging Face and can be accessed [here](https://huggingface.co/datasets/raishish/algd).

---

## Repository Features

- **Evaluation Notebooks**: Jupyter notebooks for evaluating LLMs (GPT-4o-mini, LLaMa-3.1, Gemma2) on the ALGD dataset.
- **Precomputed Results**: CSV files containing evaluation results for multiple models across different digit complexities.
- **Digit-Wise Accuracy Analysis**: Digit-wise accuracy evaluation.
- **Reproducibility**: Scripts and configurations to reproduce experiments from the research report *"Length Generalization of Arithmetic Performance"*.

---

## Repository Structure

```plaintext
.
├── evaluation
│   ├── gemma-2b-Instruct-ALGD-eval.ipynb      # Evaluation notebook for Gemma 2B
│   ├── llama-3.1-70B-Instruct-ALGD-eval.ipynb # Evaluation notebook for LLaMa 70B
│   └── llama-3.1-8B-Instruct-ALGD-eval.ipynb  # Evaluation notebook for LLaMa 8B
├── results
│   ├── gemma-2b-it/                      # Results for Gemma 2B
│   ├── gpt-4o-mini/                      # Results for GPT-4o-mini
│   ├── llama-3.1-70b/                    # Results for LLaMa 70B
│   └── llama-3.1-8b/                     # Results for LLaMa 8B
├── length-generalization-of-arithmetic-performance.pdf # Research paper
├── LICENSE                               # License file
└── README.md                             # Documentation
```

---

## Usage

### 1. Clone the Repository
```bash
git clone git@github.com:raishish/arithmetic-interp.git
cd arithmetic-interp
```

### 2. Install Dependencies
Install Python dependencies using `pip`:
```bash
pip install -r requirements.txt
```

### 3. Download the Dataset
The ALGD dataset is available on Hugging Face. Download it using the `datasets` library:
```python
from datasets import load_dataset
dataset = load_dataset("algd")
```

Alternatively, visit the [Hugging Face page](https://huggingface.co/datasets/raishish/algd) to explore or download the dataset.

### 4. Run Evaluation Notebooks
Use the provided Jupyter notebooks in the `evaluation/` directory to evaluate models on the ALGD dataset. For example:
```bash
jupyter notebook evaluation/gpt-4o-mini-ALGD-eval.ipynb
```

### 5. Analyze Results
Precomputed results are available in the `results/` directory as CSV files. These files include overall accuracy and digit-wise accuracy for each model and task.

---

## Results Summary

The repository includes precomputed results for several state-of-the-art LLMs:
1. **GPT-4o-mini**
2. **LLaMa-3.1 (70B and 8B variants)**
3. **Gemma-2B**

Key observations:
- Models perform well on simpler tasks (e.g., 4-digit addition or 3-digit multiplication).
- Accuracy declines sharply with increasing numerical complexity or unique digit counts.
- Digit-wise analysis reveals that models often generate accurate first and last digits but struggle with middle digits in high-complexity tasks.

Refer to the `results/` directory for detailed performance metrics.

---

## Citation

If you use this repository or the ALGD dataset in your research, please cite:

```
@article{rai2024arithmetic-length-generalization-performance,
  title={Characterizing arithmetic length generalization performance in large language models},
  author={Rai, Ashish and Peddaputha, Akash and Gupta, Aman},
  year={2024},
  month={Dec},
  url={https://raishish.github.io/blog/2025/characterizing-arithmetic-length-generalization}
}
```

---

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for more details.
