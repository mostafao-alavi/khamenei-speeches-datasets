# 🇫🇷 Jeux de Données Structurés des Discours de l'Ayatollah Khamenei pour l'IA
### Formats Haute Performance Parquet, JSONL et Base SQLite FTS5 pour le Traitement du Langage Naturel

---

## 📌 Présentation
Ce dépôt fournit des jeux de données prêts pour la production, spécialement structurés pour les chercheurs en TAL (Traitement Automatique du Langage) et les ingénieurs IA travaillant sur les pipelines RAG (Retrieval-Augmented Generation) et l'entraînement de modèles de langage.

---

## 📦 Formats Disponibles
1. **Parquet (`exports/khamenei_speeches_corpus.parquet`) :** Format colonnaire haute performance (13,6 Mo) pour requêtes analytiques instantanées avec Pandas et DuckDB.
2. **JSON Lines (`exports/khamenei_speeches_corpus.jsonl`) :** Idéal pour le fine-tuning LLM et l'intégration dans Hugging Face Datasets.
3. **SQLite FTS5 (`database/speeches_fts.db`) :** Moteur de recherche plein texte intégré pour des recherches lexicales rapides.
