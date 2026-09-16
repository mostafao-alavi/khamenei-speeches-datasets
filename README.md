# 📊 Khamenei Speeches Processed AI Datasets (Parquet, JSONL, SQLite FTS5)
### High-Performance Structured Datasets for AI, NLP & RAG / مجموعه‌داده‌های استاندارد هوش مصنوعی، متن‌کاوی و RAG

[![Format: Parquet](https://img.shields.io/badge/Format-Parquet-orange.svg)](https://github.com/mostafao-alavi/khamenei-speeches-datasets)
[![Format: JSONL](https://img.shields.io/badge/Format-JSONL-yellow.svg)](https://github.com/mostafao-alavi/khamenei-speeches-datasets)
[![Database: SQLite_FTS5](https://img.shields.io/badge/Database-SQLite_FTS5-blue.svg)](https://github.com/mostafao-alavi/khamenei-speeches-datasets)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

---

## 🌐 Ecosystem Repositories / ریپازیتوری‌های سه‌گانه پروژه
| Repository | Description | Link |
| :--- | :--- | :--- |
| 📂 **`khamenei-speeches-data`** | آرشیو درختی متن کامل سخنرانی‌ها به تفکیک سال و ماه (Markdown & PDF) | [مشاهده ریپو](https://github.com/mostafao-alavi/khamenei-speeches-data) |
| 📊 **`khamenei-speeches-datasets`** | دیتاست‌های آماده هوش مصنوعی و تحلیل داده (Parquet, JSONL, SQLite FTS5) | [مشاهده ریپو](https://github.com/mostafao-alavi/khamenei-speeches-datasets) |
| ⚙️ **`khamenei-speeches-tools`** | ابزارها و کدهای خزشگر هوشمند، ممیزی، حذف تکراری‌ها و خط لوله استخراج | [مشاهده ریپو](https://github.com/mostafao-alavi/khamenei-speeches-tools) |

---

## 🌍 Multilingual Navigation
- [🇮🇷 فارسی (Persian)](#فارسی)
- [🇬🇧 English](#english)
- [🇸🇦 العربية (Arabic)](#العربية)
- [🇨🇳 中文 (Chinese)](#中文)
- [🇫🇷 Français (French)](#français)
- [🇹🇷 Türkçe (Turkish)](#türkçe)
- [🇷🇺 Русский (Russian)](#русский)

---

<a name="فارسی"></a>
## 🇮🇷 فارسی
### درباره دیتاست‌ها
این مخزن میزبان فایل‌های خروجی و پردازش‌شده سخنرانی‌های حضرت آیت‌الله خامنه‌ای در قالب‌های بهینه و استاندارد بین‌المللی برای کاربردهای **هوش مصنوعی (AI)، خط‌لوله‌های RAG، پیش‌آموزش و فاین‌تیون مدل‌های زبانی (LLM Fine-Tuning) و پردازش زبان طبیعی (NLP)** است.

### فرمت‌های ارائه‌شده
1. **`exports/khamenei_speeches_corpus.parquet`**:
   - حجم تقریبی: ۱۳.۶ مگابایت (فشرده‌سازی ستونی Snappy)
   - مناسب برای بارگذاری فوق‌سریع در Pandas، Polars، PyArrow، DuckDB و Spark.
2. **`exports/khamenei_speeches_corpus.jsonl`**:
   - مناسب برای پایپ‌لاین‌های HuggingFace Datasets، LangChain، LlamaIndex و وکتور دیتابیس‌ها.
3. **`database/speeches_fts.db`**:
   - پایگاه داده سبک SQLite همراه با جدول جستجوی تمام‌متن مجهز به توکنایزر یونیکد (FTS5 unicode61).

### نمونه کد استفاده در پایتون (Python)
```python
import pandas as pd

# خواندن مستقیم دیتاست پارکت
df = pd.read_parquet("exports/khamenei_speeches_corpus.parquet")
print(f"تعداد سخنرانی‌ها: {len(df)}")
print(df[["solar_date", "title", "word_count"]].head())
```

---

<a name="english"></a>
## 🇬🇧 English
### Overview
This repository provides production-ready structured datasets containing over 1,066 full official speeches (3.15M+ words) from 1979 to 2026 for AI, Retrieval-Augmented Generation (RAG), and NLP workflows.

### Available Formats
- **Parquet (`exports/khamenei_speeches_corpus.parquet`)**: Columnar storage for rapid analytical queries.
- **JSON Lines (`exports/khamenei_speeches_corpus.jsonl`)**: Line-by-line format for LLM fine-tuning and embeddings.
- **SQLite FTS5 (`database/speeches_fts.db`)**: Indexed full-text search database.

---

<a name="العربية"></a>
## 🇸🇦 العربية
### نظرة عامة
يوفر هذا المستودع مجموعات بيانات مهيكلة وعالية الأداء لخطابات وبيانات السيد علي الخامنئي بتنسيقات متطورة (Parquet و JSONL و SQLite) المجهزة خصيصاً لتطبيقات الذكاء الاصطناعي وخطوط أنابيب RAG وتدريب النماذج اللغوية الكبيرة.

---

<a name="中文"></a>
## 🇨🇳 中文
### 概述
本仓库提供阿亚图拉·赛义德·阿里·哈梅内伊演讲的高性能结构化数据集（Parquet、JSONL 和 SQLite FTS5），专为人工智能、RAG 和 NLP 研究优化。
