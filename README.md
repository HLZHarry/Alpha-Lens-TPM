# 🚀 Hybrid AI-Quant Strategy: Regime-Aware Factor Investing

---

## 📌 Project Overview

This project implements a **Multi-Phase Quantitative Pipeline** that combines traditional technical factors with **Retrieval-Augmented Generation (RAG)** to predict stock returns.

The core thesis is that quantitative factors (Momentum, RSI) perform differently under varying macro-economic regimes. By using an **LLM-based Macro Agent**, this strategy dynamically adjusts its exposure based on Federal Reserve sentiment.

---

## 🛠️ The 4-Phase Architecture

### Phase 1: Multi-Source Data Ingestion

- **Market Data:** Scraped 5 years of historical price data for a diversified universe (S&P 500 and TSX) using `yfinance`.
- **Macro Data:** Automated scraping of Federal Reserve Statements and Minutes (2021–2026) directly from the [Federal Reserve Board website](https://www.federalreserve.gov).

### Phase 2: Multi-Factor Engineering

Generated a library of institutional-grade features:

| Factor | Description |
|---|---|
| **Momentum** | 1-month and 3-month Log Returns |
| **Volatility** | 21-day rolling standard deviation |
| **Technical Strength** | RSI (Relative Strength Index) to detect overbought/oversold conditions |
| **Trend Health** | Price relative to the 200-Day Moving Average (`MA200`) |

### Phase 3: Institutional RAG Intelligence Engine

- **Vector Database:** Implemented `ChromaDB` to store years of Fed communications.
- **Domain-Specific Embeddings:** Utilized [`ProsusAI/finbert`](https://huggingface.co/ProsusAI/finbert) (Hugging Face) to ensure financial nuances are captured in the vector space.
- **Contextual Scoring:** Developed a RAG pipeline using `OpenAI GPT-4o`. For every meeting date, the system retrieves the most relevant historical context to score the current **Hawkish vs. Dovish** tilt relative to past cycles.

### Phase 4: Predictive Modeling & Backtesting

- **Model:** `XGBoost Regressor` to find non-linear relationships between macro sentiment and technical factors.
- **Validation:** Walk-Forward Validation (out-of-sample testing from 2025 onwards).
- **Key Metric:** Sharpe Ratio — evaluated against a Buy-and-Hold benchmark to prove superior risk-adjusted returns.

---

## 📊 Key Results & Insights

- **Alpha Generation:** The Hybrid Strategy successfully identified high-volatility regimes (e.g., April 2025), pulling into cash to avoid significant drawdowns.
- **Risk Management:** By integrating AI Sentiment, the model achieved a higher Sharpe Ratio than the market, providing a smoother equity curve.
- **Feature Importance:** Post-model analysis confirmed that `AI_Sentiment` was a **top-3 predictive factor**, validating the inclusion of unstructured alternative data.

---

## 🧰 Tech Stack

| Layer | Tools |
|---|---|
| Data Ingestion | `yfinance`, `requests`, `BeautifulSoup` |
| Vector Memory | `ChromaDB`, `ProsusAI/finbert` |
| LLM Reasoning | `OpenAI GPT-4o` |
| ML Modeling | `XGBoost`, `scikit-learn` |
| Data Processing | `pandas`, `numpy` |
