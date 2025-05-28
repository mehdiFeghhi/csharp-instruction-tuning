
# Instruction-Tuned C# Code Models

This repository accompanies our paper:

> **Data Generation and Model Training for Large Language Models: A Comprehensive Approach to Code Generation**  


## 📌 Abstract

The effectiveness of large language models (LLMs) in code generation has been demonstrated across several mainstream languages, yet their performance on industrially critical languages like **C#** remains underexplored—particularly in instruction-based, conversational settings.  
In this project, we present a scalable pipeline for generating high-quality **instruction-tuning datasets** from both public (The Stack [1]) and proprietary enterprise C# codebases.

We fine-tuned three open-source LLMs on this dataset:

- **Mistral Instruct v3 7B**
- **Hermes-3 LLaMA 3.1 8B**
- **Qwen2.5-Coder 7B Instruct**

Using **CodeBLEU** as the benchmark metric, our results show substantial improvement across lexical, syntactic, and semantic dimensions—especially on domain-specific, enterprise-level test sets.

## 🚀 Model Variants

We fine-tuned the following base models:



Each model was trained on the same C# instruction dataset and evaluated using the same test splits.

## 📊 Evaluation Results

Evaluation was performed using **CodeBLEU** on both open and proprietary benchmarks.


## 📁 Dataset

We release the full C# instruction-tuning dataset used in this work:

🔗 **[View on Hugging Face →](https://huggingface.co/datasets/MehdiFe/csharp-instruction-Dataset)**

You can load the dataset directly using 🤗 Datasets:

```python
from datasets import load_dataset

dataset = load_dataset("MehdiFe/csharp-instruction-Dataset")
````

### Dataset Stats

* Total files: 4,000
* Avg. tokens per sample: \~830
* Domains: GitHub (The Stack v1.2, permissively licensed) + proprietary enterprise code
* Format: Instruction–response pairs derived from semantically structured C# source files

## 🧠 Methodology Highlights

* 🔍 **Domain-Aware Filtering**: Public and proprietary C# data was filtered using license checkers, popularity metrics, and temporal constraints.
* 📐 **Instruction Generation**: Code samples were converted into rich prompts using structured templates (e.g., method explanation, namespace, pseudocode).
* 🧪 **Validation**: Feedback from 30 professional C# developers guided the instruction template refinement.
* 🔁 **Fine-Tuning**: Each model was trained using LoRA-based adapters with 3–5 epochs and evaluated using CodeBLEU.

## 📚 Citation

If you use our dataset or models, please cite the following:

```bibtex
@misc{feizollahi2025csharp,
  title={Data Generation and Model Training for Large Language Models: A Comprehensive Approach to Code Generation},
  author={Mehdi Feghhi},
  year={2025},
  note={Inprocess},
}
```

## 📎 Related Resources

* 📂 [The Stack dataset (BigCode)](https://huggingface.co/datasets/bigcode/the-stack)
* 📄 [CodeBLEU evaluation metric](https://github.com/microsoft/CodeXGLUE/tree/main/Code-Code/code-to-code-trans/CodeBLEU)

## 📄 License

* Code: MIT
* Dataset: MIT (via Hugging Face Hub)

---




