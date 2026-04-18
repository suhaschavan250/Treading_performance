# Market Sentiment vs Trader Performance  
### Behavioural Insights and Strategy Implications from Hyperliquid Data

---

## Objective

The objective of this project is to analyze how **market sentiment (Fear vs Greed)** influences trader behaviour and performance on Hyperliquid.

By combining market sentiment data with historical trading activity, the analysis aims to uncover patterns in:

- profitability
- trading behaviour
- risk-taking
- directional bias
- trading consistency

The ultimate goal is to derive **data-driven trading insights and strategy ideas** that adapt to different market sentiment conditions.

---

## Datasets Used

### 1. Market Sentiment Dataset
Daily sentiment classification representing overall market psychology.

Key fields:
- date
- classification (Fear, Greed, Extreme Fear, Extreme Greed, Neutral)
- sentiment value score

---

### 2. Hyperliquid Historical Trader Dataset
Trade-level dataset representing trader activity.

Key fields:
- account
- coin
- execution price
- trade size (USD)
- trade direction (long/short)
- timestamp
- closed PnL (realized profit/loss)
- transaction identifiers

---

## Methodology

### Data Preparation
- Converted timestamps into date format
- Merged trading dataset with sentiment dataset using date
- Checked missing values and ensured consistency in key variables

---

### Feature Engineering

Trade-level data was aggregated at **account–date level** to create daily behavioural and performance indicators.

Key metrics created:

| Metric | Description |
|-------|------------|
| daily_pnl | total profit per trader per day |
| win_rate | proportion of profitable trades |
| avg_trade_size | average position size per day |
| num_trades | number of trades executed per day |
| long_short_ratio | ratio of long trades to short trades |
| daily_volume | total traded value per day |
| profit_per_trade | average profit per executed trade |
| aggressive_ratio | proportion of aggressive trades |
| leverage_proxy | proxy for trader exposure intensity |

These metrics capture trader behaviour and performance under varying market conditions.

---

## Trader Segmentation

Traders were segmented using quantile-based grouping:

### Frequent vs Infrequent Traders
Based on number of trades per day.

### High vs Low Leverage Traders
Based on leverage proxy values.

### Consistent vs Inconsistent Traders
Based on stability of daily pnl using standard deviation.

Segmentation helps identify differences in behaviour and performance across trader types.

---

## Key Analysis Areas

The analysis evaluates how sentiment influences:

### Performance
- daily pnl
- win rate
- profit consistency

### Behaviour
- trading frequency
- position sizing
- risk exposure
- directional bias

### Relationships examined
- sentiment vs pnl
- sentiment vs win rate
- sentiment vs trading activity
- sentiment vs position size
- sentiment vs directional bias
- trading activity vs performance quality

Visualization techniques were used to compare behaviour across sentiment regimes.

---

## Key Insights

### Fear regimes create strong profit opportunities
Highest average pnl observed during Fear conditions, suggesting volatility-driven opportunity environments.

### Extreme Greed improves trade accuracy
Highest win rate and highest proportion of profitable trading days occur during Extreme Greed.

### Trading activity increases during uncertainty
Highest number of trades observed during Extreme Fear, indicating behavioural response to volatility.

### Position sizing reflects perceived opportunity
Largest average trade sizes occur during Fear, suggesting traders increase exposure during volatile markets.

### Traders exhibit structural long bias
Long trades dominate across sentiment regimes, especially during Extreme Fear conditions.

---

## Strategy Recommendations

### 1. Volatility Participation during Fear
Increase participation during Fear regimes to capture volatility-driven opportunities while maintaining disciplined exposure.

### 2. Momentum Alignment during Extreme Greed
Focus on directional trades aligned with strong market trends when sentiment is highly optimistic.

### 3. Sentiment-aware Position Sizing
Adjust capital exposure based on predictability of market conditions rather than increasing size purely due to volatility.

### 4. Directional Bias Discipline
Recognize structural long bias and avoid entering crowded positions during highly optimistic sentiment environments.

---

## Tools Used

- Python
- Pandas
- Matplotlib

---

## Output

Final engineered dataset:

daily_metrics.csv

This dataset can be used for:

- visualization tools (Tableau, Power BI)
- modelling
- dashboard development
- further behavioural analysis

---
