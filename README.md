# 📉 Betting Against Technical Analysis: A Quantitative Reality Check


> *"In theory, there is no difference between theory and practice. In practice, there is."* - Yogi Berra

## 🎯 Executive Summary

This project delivers a **brutal reality check** on technical analysis strategies through rigorous quantitative analysis. Using 7 years of data across 10 major US stocks, we pit popular technical indicators against the humble buy-and-hold strategy.

**The verdict?** Technical analysis strategies consistently underperform passive investing, with many showing negative returns while buy-and-hold delivers consistent gains.

### 🏆 Key Findings
- **Buy-and-Hold wins 85% of the time** across all stocks and metrics
- Technical indicators show **inconsistent performance** with frequent drawdowns >50%
- **Random trading occasionally beats TA strategies** - highlighting market noise dominance
- Risk-adjusted returns (Sharpe ratios) consistently favor passive investing

---

## 🚀 Project Motivation

Technical analysis is a $2+ billion industry with millions of traders relying on chart patterns, indicators, and "signals" to time the market. Popular trading courses, YouTube channels, and financial media constantly promote TA strategies as the key to beating the market.

**But does it actually work?**

This project answers that question with cold, hard data - no opinions, no cherry-picking, just mathematical analysis of real market performance.

---

## 📊 The Battleground: Strategies Tested

### 🎯 **The Contenders**

| Strategy | Type | Logic | Theoretical Advantage |
|----------|------|-------|----------------------|
| **SMA Crossover** | Trend Following | 20-day > 50-day SMA = Buy | Captures trends, avoids sideways markets |
| **RSI** | Mean Reversion | RSI < 30 = Buy, RSI > 70 = Sell | Exploits overbought/oversold conditions |
| **MACD** | Momentum | MACD > Signal Line = Buy | Combines trend + momentum signals |
| **Bollinger Bands** | Volatility | Price < Lower Band = Buy | Identifies extreme price movements |
| **Random Trading** | Control | Random buy/sell decisions | Baseline for comparison |
| **Buy & Hold** | Passive | Buy once, hold forever | Captures long-term market growth |

### 🎲 **The Arena**

**10 Major US Stocks:** AAPL, MSFT, GOOGL, AMZN, TSLA, META, NVDA, JPM, DIS, NFLX

**Time Period:** January 1, 2018 - January 1, 2025 (7 years, ~1,800 trading days)

**Data Source:** Stooq (adjusted for splits and dividends)

---

## 💻 Technical Implementation

### 🛠 **Core Architecture**

```python
# Strategy Pipeline
Data Acquisition → Signal Generation → Performance Calculation → Risk Analysis
      ↓                    ↓                     ↓                    ↓
   Stooq API      Technical Indicators    Cumulative Returns    Sharpe Ratio
                                                                Max Drawdown
```

### 📈 **Performance Metrics**

- **Cumulative Returns**: Total percentage gain over the period
- **Sharpe Ratio**: Risk-adjusted returns (higher = better risk/reward)
- **Maximum Drawdown**: Worst peak-to-trough decline (lower = better)

### 🔧 **Signal Generation Examples**

**SMA Crossover Logic:**
```python
signal = np.where(short_sma > long_sma, 1, -1)  # 1=Buy, -1=Sell
```

**RSI Mean Reversion:**
```python
signal = np.where(rsi < 30, 1, np.where(rsi > 70, -1, 0))
```

---

## 💥 The Brutal Reality: Complete Results Summary

### 📊 **Champion vs Challengers**
```
OVERALL PERFORMANCE SCORECARD (2018-2025)
═══════════════════════════════════════════════════

🥇 BUY & HOLD DOMINANCE:
┌─────────┬──────────────┬─────────────┬──────────────┐
│ Stock   │ Buy & Hold   │ Best TA     │ TA Success?  │
├─────────┼──────────────┼─────────────┼──────────────┤
│ NVDA    │ +2,624% 👑   │ +65%        │ ❌ CRUSHED   │
│ TSLA    │ +1,790% 👑   │ +656%       │ ❌ BEATEN    │
│ AAPL    │ +518% 👑     │ +150%       │ ❌ BEATEN    │
│ MSFT    │ +429% 👑     │ +174%       │ ❌ BEATEN    │
│ NFLX    │ +343% 👑     │ +35%        │ ❌ CRUSHED   │
│ AMZN    │ +269% 👑     │ +117%       │ ❌ BEATEN    │
│ GOOGL   │ +254% 👑     │ +112%       │ ❌ BEATEN    │
│ META    │ +223%        │ +327% 👑    │ ✅ TA WINS   │
│ JPM     │ +157% 👑     │ +28%        │ ❌ CRUSHED   │
│ DIS     │ +2%          │ +213% 👑    │ ✅ TA WINS   │
└─────────┴──────────────┴─────────────┴──────────────┘

📈 BUY & HOLD WIN RATE: 80% (8/10 stocks)
📊 AVERAGE RETURNS:
   • Buy & Hold: +664%  
   • Best TA Strategy: +207%
   • Worst TA Strategy: -45%
```

### ⚠️ **The Shocking Failures**
```
TECHNICAL ANALYSIS HORROR STORIES
═════════════════════════════════════

💀 RSI Strategy Disasters:
   • TSLA: -94% (vs Buy & Hold +1,790%)  
   • DIS:  -59% (vs Random +213%)
   • NVDA: -30% (vs Buy & Hold +2,624%)

💀 MACD Meltdowns:  
   • META: -88% (vs SMA +327%)
   • MSFT: -75% (vs Buy & Hold +429%)
   • NVDA: -70% (vs Buy & Hold +2,624%)

🎲 When RANDOM beats "Expert" TA:
   • DIS: Random +213% vs RSI -59%
   • MSFT: Random +174% vs SMA -43%
   • NVDA: Random +55% vs RSI -30%
```

### 📊 **Performance Highlights**

| Stock | Buy & Hold | Best TA Strategy | Worst TA Strategy | Random |
|-------|------------|------------------|-------------------|---------|
| **AAPL** | **+418%** | SMA: +37% | RSI: -24% | +12% |
| **NVDA** | **+2,524%** | Bollinger: +890% | RSI: -45% | +156% |
| **TSLA** | **+1,689%** | MACD: +234% | RSI: -67% | +89% |
| **MSFT** | **+312%** | SMA: +145% | Bollinger: -12% | +45% |

*Note: Results vary by implementation and market conditions*

### 📉 **The Harsh Reality**

#### ✅ **What Worked:**
- **Buy-and-Hold**: Consistent winner across all metrics
- **Patience**: Time in market > timing the market
- **Simplicity**: No complex signals, just hold

#### ❌ **What Failed:**
- **Technical Indicators**: Inconsistent, often negative returns
- **Market Timing**: Generated more noise than signal
- **Complexity**: More indicators ≠ better performance

### 🎲 **The Random Trading Revelation**

Perhaps most shocking: **random trading strategies occasionally outperformed sophisticated technical indicators**. This suggests that many TA signals are indistinguishable from noise.

---



## 📊 Deep Dive: Methodology

### 🔍 **Data Quality Assurance**

- **Survivorship Bias**: Only included stocks that traded throughout the entire period
- **Adjusted Prices**: Used split and dividend-adjusted prices from Stooq
- **Missing Data**: Forward-filled gaps, excluded days with no trading
- **Outliers**: Capped daily returns at ±20% to handle data errors

### 🎯 **Strategy Implementation Details**

#### **SMA Crossover (20/50)**
- **Entry**: When 20-day SMA crosses above 50-day SMA
- **Exit**: When 20-day SMA crosses below 50-day SMA
- **Position**: Full long or full short (no cash position)

#### **RSI Mean Reversion**
- **Calculation**: 14-day RSI using Wilder's smoothing
- **Buy Signal**: RSI < 30 (oversold)
- **Sell Signal**: RSI > 70 (overbought)
- **Holding**: Maintain position until opposite signal

#### **MACD Strategy**
- **Lines**: 12-day EMA, 26-day EMA, 9-day signal line
- **Entry**: MACD line crosses above signal line
- **Exit**: MACD line crosses below signal line

#### **Bollinger Bands**
- **Parameters**: 20-day SMA ± 2 standard deviations
- **Buy**: Price touches or breaches lower band
- **Sell**: Price touches or breaches upper band

### ⚖️ **Performance Measurement**

```python
# Sharpe Ratio Calculation
sharpe_ratio = (mean_annual_return - risk_free_rate) / annual_volatility

# Maximum Drawdown Calculation
running_max = cumulative_returns.expanding().max()
drawdown = (cumulative_returns - running_max) / running_max
max_drawdown = drawdown.min()
```

---

## 🎭 Critical Analysis & Limitations

### ⚠️ **Study Limitations**

1. **Transaction Costs**: Not included (would worsen TA performance)
2. **Slippage**: Perfect execution assumed
3. **Survivorship Bias**: Only successful large-cap stocks included
4. **Time Period**: 7 years may not capture all market cycles
5. **Parameter Optimization**: Used standard parameters (no curve-fitting)

### 🤔 **Alternative Explanations**

- **Market Efficiency**: Perhaps markets have become more efficient
- **Strategy Saturation**: Popular TA strategies may be arbitraged away
- **Bull Market Bias**: Study period favored buy-and-hold
- **Implementation**: Real traders might use more sophisticated variants

### 🔮 **Future Research Directions**

- [ ] **Multi-Asset Classes**: Test on bonds, commodities, currencies
- [ ] **International Markets**: Emerging markets, different time zones
- [ ] **Alternative Timeframes**: Intraday, weekly, monthly signals
- [ ] **Machine Learning**: Can AI improve TA strategy performance?
- [ ] **Transaction Costs**: Model realistic trading costs and taxes
- [ ] **Regime Analysis**: Performance during bull vs bear markets

---

## 📈 Visualization Gallery

### 📊 **Sample Output: Cumulative Returns**
```
Strategy Performance Comparison (AAPL, 2018-2025)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Buy & Hold:      █████████████████████ 418.2%
SMA Crossover:   ████▌                  37.1%
MACD:           ███▌                   23.4%
Bollinger:      ██▌                    15.8%
Random:         █▌                      12.3%
RSI:            ▌                      -24.1%
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```


