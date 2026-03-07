# Alpha-Lens-TPM
A Hybrid AI/ML framework for regime-aware portfolio tilt and alpha generation.

# Alpha-Lens-TPM: Hybrid Portfolio Intelligence 🏛️🤖

### Executive Summary
`Alpha-Lens-TPM` is an end-to-end investment intelligence pipeline designed for institutional "Total Portfolio" management. It bridges the gap between **Quantitative Factor Research** and **Unstructured Macro Insights** using a Hybrid AI/ML architecture.

### 🏗️ The Hybrid Architecture
This project implements the "Production Pipeline" methodology:
1. **The Context Engine (LLM/RAG):** Extracts regime signals (Inflation, Volatility, Sentiment) from unstructured macro reports.
2. **The Quant Engine (ML):** A multi-factor ranking model (XGBoost) that identifies high-quality equity leaders.
3. **The Integrator:** A dynamic optimization layer that "tilts" the portfolio based on the AI-identified regime.

### 🛠️ Tech Stack
- **Languages:** Python (SQL for data simulation)
- **ML Frameworks:** Scikit-learn, XGBoost
- **AI/NLP:** OpenAI/Gemini API (for RAG-lite macro analysis)
- **Data:** yfinance (Market Data), Fed/FRED API (Macro Data)
- **Validation:** SHAP (Interpretability), Combinatorial Purged Cross-Validation

### 🚀 Roadmap
- [ ] Phase 1: Ingestion of Total Market Diversified Universe
- [ ] Phase 2: Feature Engineering (Quality & Momentum Factors)
- [ ] Phase 3: LLM Macro-Sentiment Agent
- [ ] Phase 4: Regime-Switching Backtest
