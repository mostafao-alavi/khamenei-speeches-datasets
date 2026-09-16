# 🇬🇧 Khamenei Speeches Processed AI Datasets (Parquet, JSONL, SQLite FTS5)
### High-Performance Structured Datasets Optimized for Large Language Models, RAG Pipelines & Computational Text Analytics

---

## 📌 Executive Overview
This repository provides production-grade structured datasets encapsulating 47 years of official speech transcripts (1979–2026 / 1357–1404 SH). Engineered specifically for data scientists, NLP researchers, and LLM engineers, the corpus is offered in multiple optimized formats designed for zero-latency loading, high compression, and out-of-the-box compatibility with modern AI stacks.

---

## 📦 Dataset Artifacts & Technical Specifications

### 1. Columnar Parquet (`exports/khamenei_speeches_corpus.parquet`)
- **Size:** ~13.6 MB (Snappy compressed)
- **Target Use:** Columnar analytics, vectorized queries, DuckDB, Polars, Pandas, Apache Arrow, and PySpark.
- **Advantage:** Enables instant predicate pushdown filtering by date or word count without decoding the massive text column into RAM.

### 2. Streamable JSON Lines (`exports/khamenei_speeches_corpus.jsonl`)
- **Size:** ~30.2 MB (Plaintext UTF-8)
- **Target Use:** Hugging Face Datasets integration, LlamaIndex, LangChain, OpenAI / Anthropic / Gemini fine-tuning, and embedding pipelines.
- **Advantage:** Line-delimited format enabling low-memory streaming and chunking for vector database ingestion.

### 3. Standalone SQLite FTS5 Database (`database/speeches_fts.db`)
- **Engine:** SQLite virtual table indexing with the `unicode61` tokenizer.
- **Target Use:** Instant keyword discovery, boolean querying, and text snippet extraction without requiring Elasticsearch or third-party servers.

---

## 📑 Data Schema Definition
| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Canonical speech ID from the official registry |
| `year` | Integer | Hijri Shamsi year of the address (1357 to 1404) |
| `solar_date` | String | Standardized date formatted as `YYYY/MM/DD` |
| `title` | String | Official address title |
| `url` | String | Permanent canonical source hyperlink |
| `has_pdf` | Integer | Flag (`1` or `0`) indicating presence of archived official PDF |
| `word_count` | Integer | Total verified word count of the unabridged transcript |
| `char_count` | Integer | Total character count |
| `content` | String | Full, unabridged, and normalized transcript text |
