# Simple Trading Simulator 

## Overview
This simple trading simulator was built using Python to backtest a trading strategy based on two technical indicators: the Exponential Moving Average (EMA) and the Relative Strength Index (RSI). The system was simulated on historical market data, and a trading strategy was implemented with the following conditions:

### Signals:
1. **Buy Signal**: The 10-day EMA crosses above the 20-day EMA, and the 14-day RSI is below 30.
2. **Sell Signal**: The 10-day EMA crosses below the 20-day EMA, and the 14-day RSI is above 70.
3. **Exit Signals**:
   - The trade should stop if it incurs a 5% loss from the entry price.
   - The trade should book a profit if it gains 10% from the entry price.

### Initial Conditions:
- **Initial Capital**: $10,000
- **Transaction Fees**: Ignored for simplicity (no transaction fees considered).
- **Data Source**: The system uses historical data provided in the `msft.csv` file.

---

## Key Results
- **Total Profit/Loss**: $13,467.15
- **Total Percentage Return**: 134.67%
- **Total Number of Trades**: 30

---

## Trading Strategy Observations
- **RSI Adjustment**: In the provided dataset, there were days with missing data points. To account for this, I used an RSI value of 50 (a neutral value) for those missing points. This adjustment allowed the strategy to generate more data points for the backtest.
  
- **Market Trend**: The market was predominantly in an upward trend throughout the simulation period. Since the RSI did not often reach the overbought threshold (RSI above 70), the strategy triggered more "take profit" signals rather than "sell" signals, resulting in more profitable trades. 

- **Trade Exit Points**: Most trades were closed once the 10% profit condition was met, with some trades hitting the 5% loss limit, thanks to the overall positive market trend.

---

## Visualizations

The trading simulator also produces a **Candlestick chart** that includes:
- **Candlesticks**: Representing the price action over time.
- **10 & 20-day EMA**: Plotted to show the trend-following aspects of the strategy.
- **Buy & Sell Markers**: Indicating the exact points at which the buy and sell signals occurred during the simulation.

This chart provides a clear visualization of how the strategy performed in the given market conditions.

---

## Files
1. **msft.csv**: Contains the historical market data used for simulation. This includes  dates,high,low,open and close values.
2. **ema_rsi_strategy.csv**: Detailed information about each trade, including entry and exit points, profit/loss per trade, and whether stop loss or profit targets were hit.
3. **newplot(2).png and newplot(3).png**: Visualization of the trades and strategy performance.

---

## Conclusion
The backtest results of this simple trading simulator show that the strategy performed well in an upward-trending market. The use of the 10-day and 20-day EMA crossover, combined with RSI for market conditions, provided a reliable mechanism for generating buy and sell signals. Adjustments to the RSI value for missing data did not significantly affect the performance, and the strategy was able to generate consistent profits.

To run the simulator and view the full details of the trades, 
- Clone this repository.
- install all the dependencies I recomend createing a virtual envioprment.
- run the simulator.

---

## Future Improvements
- **Transaction Costs**: Implementing transaction fees could affect the profitability of the strategy.
- **Dynamic Risk Management**: Including additional risk management features such as dynamic stop losses based on volatility.
- **Optimization**: Testing the strategy with different time frames and adjusting the RSI thresholds for better optimization.

---


