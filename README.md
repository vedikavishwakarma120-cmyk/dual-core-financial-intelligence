# dual-core-financial-intelligence
Stock price forecasting with uncertainty and explainable financial insights

# Dual-Core Financial Intelligence System

This project implements a dual-core financial intelligence system consisting of:
1. A **Predictive Core** for time-series stock price forecasting with uncertainty.
2. An **Explanatory Core** that translates model outputs into human-readable financial insights.

## Task 1: Predictive Core
- Asset: Apple Inc. (AAPL)
- Data: Daily historical stock prices (OHLCV)
- Model: SARIMA (Statistical Time Series Model)
- Forecast Horizon: 7 days
- Outputs:
  - Historical trend visualization
  - Validation on past unseen data
  - 7-day forecast
  - Confidence intervals to model uncertainty

## Task 2: Analytical Chatbot (Prototype Implementation)

The goal of Task 2 is to provide a natural language interface that explains market behavior and contextualizes numerical forecasts.

In this project, we implement the **analytical and reasoning core** of such a chatbot. Instead of directly deploying a full LLM-based conversational agent, the system focuses on extracting interpretable financial signals and generating human-readable explanations.

The current implementation:
- Analyzes recent price trends and momentum
- Quantifies market volatility using rolling statistics
- Interprets forecast uncertainty via confidence intervals
- Produces structured, explainable insights similar to a financial advisor

This design ensures that the system does not merely output predictions, but also explains *why* the model behaves in a certain way, aligning with the intent of explainable financial intelligence.

## Future Work: Full Agentic RAG-Based Financial Chatbot

The current analytical core is designed to be extensible into a fully agentic, retrieval-augmented chatbot. Planned extensions include:

- **Natural Language Interface**  
  Integrating an LLM (e.g., open-source Hugging Face models or API-based LLMs) to allow users to ask free-form questions such as:
  “Why did Apple stock drop?” or “When did Microsoft experience an uptrend?”

- **Ticker Identification & Intent Understanding**  
  Using semantic intent parsing to identify relevant tickers and query types rather than relying on keyword matching.

- **Retrieval-Augmented Generation (RAG)**  
  Scraping and indexing financial news, earnings reports, and analyst commentary into a vector database.  
  Relevant documents would be retrieved and cited to ground explanations in real-world events.

- **Multi-Agent Architecture**  
  Separating responsibilities across agents, such as:
  - A Trend Analysis Agent (price and volatility)
  - A Research Agent (news and events)
  - A Visualization Agent (plots and summaries)

- **Improved Evaluation**  
  Combining quantitative metrics with qualitative explanations to assess both forecast accuracy and explanation quality.

These extensions would transform the current prototype into a fully conversational, explainable financial intelligence system.

## Task 3 (Optional): Real-Time Intelligence — Design Thought Process

Task 3 focuses on extending the static forecasting system into a real-time financial intelligence platform capable of ingesting live market data and updating analysis dynamically.

While this project does not implement live data ingestion due to scope and time constraints, the following design outlines how the system would be upgraded in a production-ready manner.

### 1. Live Data Ingestion
A persistent connection would be established with a market data provider (e.g., via WebSocket or streaming API).
Incoming tick or minute-level price data would be appended to the existing historical dataset in real time.

To ensure continuity, the system would first backfill any missing historical data before initiating the live stream.

### 2. Real-Time Processing Pipeline
Each new data point would trigger:
- Incremental updates to rolling statistics (volatility, momentum)
- Re-evaluation of short-term trend direction
- Periodic re-forecasting using a sliding window approach

Rather than retraining models from scratch, lightweight updates or scheduled re-fits would be used to balance accuracy and latency.

### 3. Live Dashboard
A front-end dashboard would subscribe to the processed data stream and update visualizations automatically without page refresh.
Key components would include:
- Live price chart with forecast overlays
- Dynamic confidence intervals reflecting updated uncertainty
- Visual indicators for trend shifts or volatility spikes

### 4. Dynamic Alerts
Rule-based or model-driven alerting logic would monitor live prices and predictions.
Notifications could be triggered when:
- Prices cross forecasted confidence bounds
- Sudden volatility spikes occur
- Trend direction reverses

Alerts could be delivered via in-app notifications, email, or messaging services.

### 5. System Architecture
The real-time system would follow a modular architecture:
- Data Stream Module (API/WebSocket ingestion)
- Processing Engine (analytics & forecasting)
- Visualization Layer (live dashboard)
- Alerting Service (threshold-based triggers)

## Notes on Evaluation
The model is evaluated using Mean Absolute Error (MAE) on historical data.  
Absolute error values are relatively high due to long-term price growth and scale effects in stock prices.  
Future improvements include log-scaling and relative error metrics.

## Data Source
Historical stock price data sourced from **Stooq** (public financial data provider).

## Technologies Used
- Python
- Pandas, NumPy
- Statsmodels (SARIMA)
- Matplotlib
