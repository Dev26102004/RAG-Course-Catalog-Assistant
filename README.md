# 📘 RAG-Based Course Catalog Assistant

## 📌 Overview

This project implements a **Retrieval-Augmented Generation (RAG) system** to answer questions related to a university course catalog. The system retrieves relevant documents and generates structured, grounded responses using an LLM.

The assistant can answer queries about:

* Course prerequisites
* Program requirements
* Course planning
* Policies

It also ensures **safe and reliable responses** by avoiding hallucinations and providing citations.

---

## 🚀 Features

* 🔍 Semantic search using embeddings
* 📄 Document retrieval from dataset (PDF/TXT)
* 🤖 LLM-based answer generation
* 📚 Source citations for every answer
* ⚠️ Safe abstention when information is missing
* 📊 Evaluation with multiple test queries

---

## 🧠 System Architecture

1. **Data Ingestion**

   * Course catalog documents are loaded and split into chunks
   * Text is converted into embeddings

2. **Retriever**

   * Uses similarity search (FAISS)
   * Retrieves top relevant chunks for a query

3. **RAG Pipeline**

   * Combines retrieved context with user query
   * Generates structured response using LLM

4. **Output Format**

   * Answer / Plan
   * Why (reasoning)
   * Citations
   * Clarifying Questions
   * Assumptions

---

## 📂 Dataset

The dataset consists of:

* Course pages (CS, Math, etc.)
* Program requirement documents
* Academic policies

Documents were collected and structured to simulate a real university catalog.

---

## 🧪 Evaluation

### Test Setup

* Total Queries: **25**
* Query Types:

  * Direct factual questions
  * Eligibility queries
  * Course planning questions
  * Edge cases (missing information)

### Metrics

* **Answer Accuracy:** 56%
* **Citation Coverage:** 100%
* **Abstention Accuracy:** 100%

### Observations

* The system performs well on **direct factual queries**
* Accuracy decreases for:

  * paraphrased questions
  * multi-step reasoning queries
* The system reliably avoids hallucinations by abstaining when information is unavailable

---

## 📊 Example Queries

### ✅ Example 1: Factual Query

**Q:** What are prerequisites for CS310?
**A:** CS201 and CS250 are required.

---

### ✅ Example 2: Eligibility Query

**Q:** Can I take CS310 after CS201 only?
**A:** No, CS250 is also required.

---

### ⚠️ Example 3: Missing Information

**Q:** Who teaches CS310?
**A:** The system does not have that information.

---

## ⚙️ Installation

```bash
pip install -r requirements.txt
```

---

## ▶️ Usage

Run your notebook or main script and test queries like:

```python
adv_rag.query("What are prerequisites for CS310?")
```

---

## 📁 Project Structure

```
project/
├── data/
|   └── evaluation_results_auto.csv
|   └── pdfs
├── notebook/
├── README.md
├── requirements.txt
├──writeup.pdf
```

---

## 🔧 Limitations

* Struggles with **multi-step reasoning**
* Sensitive to **query phrasing**
* Retrieval may miss relevant chunks in some cases

---

## 🚀 Future Improvements

* Query normalization and expansion
* Multi-hop reasoning support
* Better retriever tuning
* Larger and more diverse dataset

---

## 🏁 Conclusion

This project demonstrates a functional RAG system capable of answering course-related queries with:

* grounded responses
* reliable citations
* safe fallback behavior

It highlights both the **strengths and limitations** of retrieval-based AI systems in real-world scenarios.
