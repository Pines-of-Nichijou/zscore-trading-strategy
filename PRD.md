# Product Requirements Document (PRD)

## 1. Introduction

This document outlines the requirements for a Pine Script strategy to be used in TradingView. The strategy combines technical analysis with automated signal generation for cryptocurrency trading, featuring integration with OKX's signal system.

## 2. Core Components

### 2.1 Technical Analysis
- Z-score based trading signals
- Multiple technical indicators (MA, EMA, RSI, MACD)
- Dynamic timeframe adaptation
- Customizable parameters for all indicators

### 2.2 Signal Integration
- OKX signal system integration
- Automated alert message generation
- Configurable position sizing
- Token-based authentication

### 2.3 Capital & Risk Management
- Initial capital configuration
- Position size percentage control
- Stop loss and take profit management
- Martingale strategy implementation
- Dynamic position sizing

## 3. Features

### 3.1 Trading Logic
- **Entry Conditions**
  - Z-score threshold crossing
  - Technical indicator confirmations
  - Combined signal validation
  - Martingale strategy implementation
    - Multiple entry positions with increasing size
    - Dynamic position size scaling using martingale multiplier
    - Maximum position count limit
    - Dynamic take-profit and stop-loss adjustments
      - Take-profit levels increase with each additional position
      - Stop-loss levels adjust to protect accumulated positions
      - Based on weighted average entry price

- **Risk Management**
  - Enhanced Stop Loss Management
    - Option to move stop loss to entry price after additional positions
    - Percentage inputs normalized (0-100%) for better usability
    - Dynamic stop-loss adjustment based on average entry
  - Dynamic Take Profit Management
    - Percentage inputs normalized (0-100%)
    - Increased targets for subsequent positions
    - Based on weighted average entry price
  - Martingale Strategy Improvements
    - Automatic position size scaling
    - Break-even stop loss option
    - Dynamic risk adjustment per position

- **Indicator Selection**
  - Z-Score Threshold Cross (optional)
  - Moving Average (optional)
  - Exponential Moving Average (optional)
  - RSI (optional)
  - MACD (optional)
  - Configurable indicator combinations

- **Martingale Strategy Details**
  - Position Multi Entry limit
  - Martingale Multiplier for position scaling
  - Entry Distance percentage requirement
  - Dynamic TP/SL adjustments
    - TP Multiplier for increased targets
    - SL Multiplier for risk adjustment
    - Move Stop To Entry Profit threshold

### 3.2 Signal Generation
- **Alert Message Structure**
  ```json
  {
    "action": "ENTER_LONG/ENTER_SHORT",
    "instrument": "<trading_pair>",
    "signalToken": "<user_token>",
    "timestamp": "yyyy-MM-dd'T'HH:mm:ssZ",
    "orderType": "market",
    "orderPriceOffset": "0.0",
    "investmentType": "percentage_investment",
    "amount": "<position_size>"
  }
  ```

- **Signal Types**
  - Entry signals (long/short)
  - Exit signals (take-profit/stop-loss)
  - Position management signals

### 3.3 Visualization
- Z-score plotting
- Technical indicator overlays
- Signal markers on chart
- Threshold level indicators

## 4. Configuration Parameters

### 4.1 Trading Parameters
- Initial capital amount
- Lookback period
- Indicator lengths
- Z-score threshold
- Risk Management Parameters
  - Stop Loss (0.1-100%)
  - Take Profit (0.1-100%)
  - Move Stop to Entry option
    - Automatically moves stop loss to break even after additional positions
    - Protects accumulated profits
    - Optional feature that can be enabled/disabled
  - Normalized percentage inputs
    - All percentage inputs use 0-100 range
    - Values automatically converted to decimals for calculations
    - More intuitive user interface

- Martingale Configuration
  - Position Multi Entry (min: 1)
  - Martingale Multiplier (min: 1.0)
  - Entry Distance (0.1-100%)
  - Move Stop To Entry Profit (0.1-100%)
  - Dynamic TP Multiplier (min: 1.0)
  - Dynamic SL Multiplier (0.1-1.0)

### 4.2 Signal Parameters
- Signal token input
- Position size (0.1-100%)
- Order type settings
- Investment type configuration

### 4.3 Indicator Parameters
- RSI Settings
  - Overbought level (0-100)
  - Oversold level (0-100)
- MACD Settings
  - Fast Length
  - Slow Length
  - Signal Length
- Indicator Length for MA/EMA calculations
- Z-Score lookback period

## 5. Technical Requirements

### 5.1 Platform Requirements
- TradingView version 6.0+
- OKXSignalLogic library (version 1)
- Valid TradingView account

### 5.2 Dependencies
- OKX signal system integration
- Real-time data feed
- Alert message capability

## 6. Implementation Notes

### 6.1 Setup Instructions
1. Configure signal token in strategy settings
2. Set desired position size percentage
3. Adjust technical indicators as needed
4. Enable automated alerts

### 6.2 Integration Points
- Entry signal generation
- Exit signal handling
- Alert message formatting
- Position management

## 7. Future Enhancements

### 7.1 Planned Features
- Machine learning integration
- Additional technical indicators
- Enhanced risk management
- Multi-exchange support

### 7.2 Potential Improvements
- Custom alert templates
- Advanced position sizing
- Portfolio management
- Performance analytics

## 8. Limitations and Constraints

- Limited to TradingView's capabilities
- Dependent on market data quality
- Alert message size restrictions
- Exchange-specific limitations

## 9. Support and Maintenance

- Regular updates for compatibility
- Bug fixes and improvements
- Documentation updates
- User support guidelines

## 10. Trade Management

### 10.1 Position Tracking
- Custom Trade type implementation
- Position size tracking
- Entry price management
- Take profit and stop loss price updates
- Multi-position handling

### 10.2 Alert Messages
- Entry alert message generation
- Exit alert message generation
- Integration with OKX signal system
- Maximum lag configuration
