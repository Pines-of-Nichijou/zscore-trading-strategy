# ZCore Trading Strategy

This repository contains the Pine Script code for the "ZCore Trading Strategy," a customizable trading strategy designed for use on the TradingView platform.

## Strategy Overview

The ZCore Trading Strategy utilizes a combination of technical indicators to generate buy and sell signals. It includes options to use Moving Averages (MA), Exponential Moving Averages (EMA), Relative Strength Index (RSI), and the Moving Average Convergence Divergence (MACD) indicator. The strategy is based on the calculation of a Z-Score to identify potential trading opportunities.

## Input Parameters

- **Initial Capital**: The starting capital for the strategy (default: 1000).
- **Lookback Period**: Number of bars used for calculations (default: 20).
- **Indicator Length**: Length for MA, EMA, and RSI calculations (default: 14).
- **Z-Score Threshold**: Threshold for generating buy/sell signals based on Z-Score (default: 1.5).
- **Stop Loss (%)**: Percentage for stop loss (default: 2%).
- **Take Profit (%)**: Percentage for take profit (default: 5%).

## Indicator Settings

- **Use Moving Average**: Enable/disable the use of Moving Average.
- **Use Exponential Moving Average**: Enable/disable the use of Exponential Moving Average.
- **Use RSI**: Enable/disable the use of RSI.
- **Use MACD**: Enable/disable the use of MACD.

## RSI Settings

- **RSI Overbought Level**: Level above which RSI is considered overbought (default: 70).
- **RSI Oversold Level**: Level below which RSI is considered oversold (default: 30).

## MACD Settings

- **MACD Fast Length**: Fast length for MACD calculation (default: 12).
- **MACD Slow Length**: Slow length for MACD calculation (default: 26).
- **MACD Signal Length**: Signal length for MACD calculation (default: 9).

## Usage

1. Copy the Pine Script code from `src/main.ps` into the TradingView Pine Script editor.
2. Adjust the input parameters and indicator settings as desired.
3. Add the script to a chart to visualize the strategy and its signals.
4. Use the strategy's buy and sell signals to inform trading decisions.

## Plotting

The strategy plots the following on the chart:
- Z-Score
- Z-Score Thresholds
- Moving Average (if enabled)
- Exponential Moving Average (if enabled)

## License

This Pine Script code is subject to the terms of the Mozilla Public License 2.0. See [LICENSE](https://mozilla.org/MPL/2.0/) for more details.
