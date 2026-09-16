# 📊 Ayatollah Khamenei Speeches Processed AI Datasets (1979–2026)
### High-Performance Columnar, Streaming & Search Datasets / مجموعه‌داده‌های پردازش‌شده هوش مصنوعی، خطوط RAG و پردازش زبان طبیعی

[![Format: Parquet](https://img.shields.io/badge/Format-Parquet_Snappy-orange.svg)](https://github.com/mostafao-alavi/khamenei-speeches-datasets)
[![Format: JSONL](https://img.shields.io/badge/Format-JSONL_Streaming-yellow.svg)](https://github.com/mostafao-alavi/khamenei-speeches-datasets)
[![Database: SQLite_FTS5](https://img.shields.io/badge/Database-SQLite_FTS5-blue.svg)](https://github.com/mostafao-alavi/khamenei-speeches-datasets)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

---

## 🌐 Project Ecosystem / اکوسیستم مخازن سه‌گانه
| Repository | Role | Content | Link |
| :--- | :--- | :--- | :--- |
| 📂 **`khamenei-speeches-data`** | **Primary Source Archive** | آرشیو درختی متن کامل سخنرانی‌ها به تفکیک سال و ماه (Markdown, JSON, HTML, PDF) | [GitHub](https://github.com/mostafao-alavi/khamenei-speeches-data) |
| 📊 **`khamenei-speeches-datasets`** | **AI & Analytics Datasets** | دیتاست‌های تجمیعی هوش مصنوعی (Parquet, JSONL, SQLite FTS5) برای RAG و LLM | [GitHub](https://github.com/mostafao-alavi/khamenei-speeches-datasets) |
| ⚙️ **`khamenei-speeches-tools`** | **Engineering & Crawler** | موتور دانلودر ضد مسدودی، ممیزی داده‌ها، و خط لوله استخراج و پاکسازی | [GitHub](https://github.com/mostafao-alavi/khamenei-speeches-tools) |

---

## 🌍 Complete Multilingual Documentation / مستندات کامل چندزبانه
برای مطالعه مستندات جامع به زبان‌های مختلف، از پیوندهای زیر استفاده کنید:
- 🇮🇷 **[فارسی (Persian)](docs/README.fa.md)** - نسخه کامل راهنمای فنی و هوش مصنوعی
- 🇬🇧 **[English (Default)](docs/README.en.md)** - Comprehensive AI & Data Science Documentation
- 🇸🇦 **[العربية (Arabic)](docs/README.ar.md)** - دليل مجموعات البيانات للذكاء الاصطناعي
- 🇨🇳 **[中文 (Chinese)](docs/README.zh.md)** - 人工智能与自然语言处理数据集指南
- 🇫🇷 **[Français (French)](docs/README.fr.md)** - Guide des Jeux de Données IA et NLP
- 🇹🇷 **[Türkçe (Turkish)](docs/README.tr.md)** - Yapay Zeka ve NLP Veri Kümeleri Rehberi
- 🇷🇺 **[Русский (Russian)](docs/README.ru.md)** - Руководство по Датасетам для ИИ и NLP

---

## ⚡ Quick-Start Code Samples

### Python (Pandas & DuckDB with Parquet)
```python
import pandas as pd

# Load high-performance Parquet file (13.6 MB)
df = pd.read_parquet("exports/khamenei_speeches_corpus.parquet")
print(f"Loaded {len(df):,} speeches spanning {df['year'].min()} to {df['year'].max()}.")
print(f"Total tokens: {df['word_count'].sum():,}")
```

### Full-Text Search with SQLite FTS5
```python
import sqlite3

conn = sqlite3.connect("database/speeches_fts.db")
c = conn.cursor()
query = "استقلال AND آزادی"
c.execute("SELECT solar_date, title, snippet(speeches_fts, 2, '<b>', '</b>', '...', 15) FROM speeches_fts WHERE content MATCH ? LIMIT 5", (query,))
for row in c.fetchall():
    print(f"[{row[0]}] {row[1]}\n{row[2]}\n")
```
