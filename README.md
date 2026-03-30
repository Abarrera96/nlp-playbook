# Practical NLP Portfolio (Python 3.11)

This repository is a portfolio-ready NLP showcase designed for recruiters, hiring managers, and technical interviewers.  
It focuses on practical, production-oriented NLP work across classical pipelines, transformer-based workflows, and OCR-driven document extraction.

## Repository Structure

```text
nlp-playbook/
|-- README.md
|-- requirements.txt
|-- .gitignore
|-- .env.example
|-- notebooks/
|   |-- 01_tfidf_with_cosine_similarity.ipynb
|   |-- 02_tfidf_with_logistic_regression.ipynb
|   |-- 03_bert_for_text_classification.ipynb
|   |-- 04_ner_with_spacy.ipynb
|   |-- 05_ner_with_bert.ipynb
|   |-- 06_question_answering_with_bert.ipynb
|   |-- 07_semantic_search_with_sentence_transformers.ipynb
|   `-- 08_document_nlp_ocr_extraction.ipynb
`-- data/
    `-- 01_data/
        `-- support_tickets_en.csv
    `-- 02_data/
        `-- support_tickets_baseline.csv
    `-- 03_data/
        `-- news_topic_synthetic.csv
    `-- 04_data/
        |-- ner_documents.csv
        `-- ner_gold_entities.csv
    `-- 05_data/
        |-- ner_bert_documents.csv
        `-- ner_bert_gold_entities.csv
    `-- 06_data/
        |-- policies.csv
        `-- qa_questions.csv
    `-- 07_data/
        |-- knowledge_base.csv
        `-- search_queries.csv
    `-- 08_data/
        `-- invoice_records.csv
```

## Installation (Python 3.11)

```bash
python3.11 -m venv .venv
source .venv/scripts/activate
pip install --upgrade pip
pip install -r requirements.txt
python -m spacy download en_core_web_sm
python -m spacy download es_core_news_sm
```

## OCR Dependency Note (Tesseract)

`pytesseract` is the Python wrapper, but **Tesseract OCR must also be installed at OS level** for Notebook 08.

```bash
sudo apt install tesseract-ocr-spa tesseract-ocr-eng
tesseract --version
```

## Notebooks Overview

1. **01_tfidf_with_cosine_similarity.ipynb**  
   Structured preprocessing + TF-IDF workflow using `scikit-learn`, with explicit training, evaluation, and inference routing over a larger ticket dataset in `data/01_data`.

2. **02_tfidf_with_logistic_regression.ipynb**  
   End-to-end baseline text classifier (TF-IDF + Logistic Regression) using `data/02_data`, with split, training, evaluation, interpretability, and inference helper.

3. **03_bert_for_text_classification.ipynb**  
   Transformer text classification workflow on `data/03_data`, including baseline comparison, DistilBERT fine-tuning, evaluation, and inference examples.

4. **04_ner_with_spacy.ipynb**  
   Practical spaCy NER extraction with measurable evaluation against gold entities from `data/04_data`.

5. **05_ner_with_bert.ipynb**  
   BERT token-classification NER on `data/05_data`, including BIO conversion, label alignment, fine-tuning, and evaluation.

6. **06_question_answering_with_bert.ipynb**  
   Extractive QA pipeline over policy datasets in `data/06_data`, with exact match/token-F1 evaluation and production-style answer helper.

7. **07_semantic_search_with_sentence_transformers.ipynb**  
   Semantic search on `data/07_data` using Sentence Transformers + FAISS, compared against TF-IDF keyword retrieval with Recall@k and MRR@k.

8. **08_document_nlp_ocr_extraction.ipynb**  
   OCR + post-processing pipeline driven by invoice records in `data/08_data`, with field-level extraction accuracy tracking.

## Why This Repository Is Relevant for Real-World NLP Roles

- Demonstrates end-to-end NLP thinking: data preparation, modeling, evaluation, and production trade-offs.
- Combines classical and modern methods, showing judgment in model selection.
- Includes document OCR extraction, which is common in enterprise automation workflows.
- Uses clear, recruiter-friendly notebook narratives with runnable code.
