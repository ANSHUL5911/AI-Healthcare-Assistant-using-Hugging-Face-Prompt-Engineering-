# 🩺 MediAssist AI — Prompt Engineering with Hugging Face

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)
![Transformers](https://img.shields.io/badge/🤗%20Transformers-Hugging%20Face-FFD21E?style=flat-square)
![Model](https://img.shields.io/badge/Model-Zephyr--7B--beta-blueviolet?style=flat-square)
![Status](https://img.shields.io/badge/Status-Complete-success?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=flat-square)

A prompt-engineering assignment that turns an open, ungated Hugging Face LLM (**Zephyr‑7B‑beta**) into a structured, role-aware **clinical decision-support assistant** — using nothing but careful prompting. No fine-tuning, no extra training data, just role prompting, context grounding, constraints, few-shot examples, chain-of-thought, and structured output design.

---

## 📋 What's in this repo

| File | Description |
|---|---|
| `MediAssist_AI_Prompt_Engineering_Chatbot.ipynb` | Main notebook — model setup + all 7 tasks + bonus challenge |
| `MediAssist_AI_Prompt_Engineering_Report (1).docx` | 3-page report: model selection, techniques, challenges, refinements |
| `README.md` | This file |
| `images` | screenshots of chatbot  |

---

## 🧠 Model Used

**[`HuggingFaceH4/zephyr-7b-beta`](https://huggingface.co/HuggingFaceH4/zephyr-7b-beta)** — a 7B instruction-tuned model, fine-tuned with **DPO (Direct Preference Optimization)** for strong instruction-following and format compliance. Chosen because it's fully ungated (no access request needed) and shares the Mistral‑7B architecture, so it can be swapped for a stronger or medically fine-tuned model (e.g. `BioMistral`) by changing a single `MODEL_NAME` string.

It's compared against `mistralai/Mistral-7B-Instruct-v0.1` in **Task 6** of the notebook.

---

## 🗂️ Tasks Covered

| # | Task | Technique Highlight |
|---|---|---|
| 1 | Interactive medical chatbot | System-prompt persona + safety guardrails |
| 2 | Patient-education prompt design | Role + context + constraints + strict Markdown format |
| 3 | Clinical note summarization | Few-shot prompting (3 worked examples) |
| 4 | Triage urgency assessment | Silent chain-of-thought reasoning |
| 5 | Structured data extraction | JSON schema + defensive parsing (regex + try/except) |
| 6 | Model comparison | Zephyr-7B-beta vs. Mistral-7B-Instruct-v0.1 |
| 7 | Prompt optimization | Before/after rewrite of a weak differential-diagnosis prompt |
| ⭐ | Bonus: role-aware template | One prompt template, four personas (doctor / nurse / student / patient) |

---

## ⚙️ Setup & Run

```bash
# 1. Install dependencies
pip install -q transformers accelerate huggingface_hub sentencepiece

# 2. Open the notebook
jupyter notebook Copy_of_MediAssist_AI_Prompt_Engineering.ipynb
```

> 💡 Recommended: run on **Google Colab** with a GPU runtime (T4 or better) — a 7B model in fp16 needs roughly 14–16 GB of VRAM.

Run the cells top to bottom. Cell 6 loads the tokenizer/model; every task afterward reuses the shared `generate_response()` wrapper.



## 📄 Full Report

See [`MediAssist_AI_Prompt_Engineering_Report (1).pdf`](./MediAssist_AI_Prompt_Engineering_Report.pdf) for the complete write-up on model selection, prompt engineering techniques, challenges faced, and before/after prompt refinements.

---

<p align="center"><sub>Built as part of a prompt engineering assignment · Hugging Face 🤗 + Transformers</sub></p>
