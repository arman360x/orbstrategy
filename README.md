# Pyramiding Strategy Indicator

This is a **Pine Script-based indicator** that implements a **pyramiding strategy** on TradingView. The strategy scales into a position by opening multiple trades based on predefined conditions. The indicator supports both **long** and **short** positions, with configurable lot sizes for each position. The exit strategy includes take-profit (TP) and stop-loss (SL) levels for each trade.

---

## Features

- **Pyramiding**: Allows multiple trades (up to 3 positions) in the same direction (long or short).
- **Configurable Lot Sizes**: Distribute the total lot size across multiple positions (30% for the first two positions, 40% for the third).
- **Customizable TP/SL**: Set different take-profit and stop-loss values for each position.
- **Flexible Time Frames**: Works on any time frame in TradingView.
- **Dynamic Entry & Exit**: The strategy dynamically enters and exits positions based on moving average crossovers.

---

## Inputs

- **Total Lot Size**: The overall position size (e.g., 1.0, 2.0).
- **Percentage for First Order**: The percentage of the total lot size allocated for the first position (default: 30%).
- **Percentage for Second Order**: The percentage of the total lot size allocated for the second position (default: 30%).
- **Percentage for Third Order**: The percentage of the total lot size allocated for the third position (default: 40%).
- **Take Profit Levels (Pips)**:
  - TP1: 10 pips (default)
  - TP2: 15 pips (default)
  - TP3: 20 pips (default)
- **Stop Loss (Pips)**: Set the stop-loss in pips for each position (default: 5 pips).

---

## How It Works

1. **Entry Condition**:
   - **Long** positions are entered when the fast moving average crosses above the slow moving average.
   - **Short** positions are entered when the fast moving average crosses below the slow moving average.

2. **Pyramiding Logic**:
   - The strategy allows up to 3 trades in the same direction (long or short). The first trade gets 30% of the total lot size, the second trade gets another 30%, and the third gets the remaining 40%.

3. **Exit Strategy**:
   - Each position has its own exit strategy based on the following:
     - Take-profit (TP) levels: Each position has a different TP (TP1, TP2, TP3).
     - Stop-loss (SL) levels: Each position has its own SL.

4. **Pyramiding Parameters**:
   - The maximum number of positions is configurable by setting the `pyramiding` parameter in the `strategy()` function to control how many trades you want to open at the same time.

---

## How to Use

1. Copy the Pine Script provided in the `pyramiding-strategy-indicator` file.
2. Open TradingView and navigate to the **Pine Script Editor**.
3. Paste the script into the editor and click on **Add to Chart**.
4. Adjust the input parameters as desired.
5. The strategy will automatically execute based on the defined conditions.

---


