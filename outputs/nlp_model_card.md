# NLP Model Card — Thesis NLP Module

**Generated:** 2026-01-02 20:45:19  
**Mode:** Unsupervised NLP (Topics + Sentiment)  
**Text column:** Policy_Text  
**Rows used:** 5  
**Sentiment method:** VADER  
**Topics (NMF):** 2  

---

## Objective
Extract themes and sentiment signals from remittance-related text when no ground-truth labels are available.

---

## Methods
- **TF-IDF:** identify highest-signal terms
- **Topic Modeling:** NMF over TF-IDF (dominant topic per document)
- **Sentiment:** VADER if available; otherwise a safe lexicon fallback

---

## Artifacts Saved
- `nlp_cleaned_text.csv`
- `nlp_top_tfidf_terms.csv`
- `nlp_topics_nmf.csv`
- `nlp_docs_with_topics.csv`
- `nlp_sentiment_scored.csv`