# 🇨🇳 阿亚图拉·哈梅内伊演讲处理后人工智能数据集
### 专为大语言模型 (LLM)、检索增强生成 (RAG) 与自然语言处理优化的 Parquet、JSONL 及 SQLite FTS5 数据集

---

## 📌 数据集概览
本仓库提供阿亚图拉·哈梅内伊历时47年（1979–2026）的全部官方演讲高精度结构化数据集。所有文本已经过严苛的清洗与全文本审计，提供极速分析与嵌入加载格式。

---

## 📦 格式规格说明
1. **列式存储 Parquet (`exports/khamenei_speeches_corpus.parquet`):** 约 13.6 MB，采用 Snappy 压缩算法，适合 DuckDB、Polars 和 Pandas 进行高并发离线分析。
2. **逐行流式 JSONL (`exports/khamenei_speeches_corpus.jsonl`):** 约 30.2 MB，符合大语言模型微调规范，适配 LangChain、LlamaIndex 及向量数据库导入。
3. **全文检索 SQLite FTS5 (`database/speeches_fts.db`):** 内置 Unicode 全文分词索引，支持亚毫秒级的关键字检索与上下文高亮。
