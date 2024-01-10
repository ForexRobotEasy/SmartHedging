# SmartHedging Expert Advisor

SmartHedging is an Expert Advisor designed to automate hedging strategies in the forex market. It calculates the optimal lot size based on user-defined risk percentage and account balance, opens initial trades, and manages hedging cycles to minimize losses and maximize profits.

## Input Parameters

- RiskPercentage: The percentage of account balance to risk per trade.
- BreakevenPercentage: The percentage of profit required to move the stop loss to breakeven.
- ProfitPercentage: The percentage of profit required to close the hedging cycle.

## Global Variables

- AccountBalance: Stores the current account balance.
- LotSize: Stores the calculated lot size for trading.
- StopLoss: Stores the current stop loss level.
- TakeProfit: Stores the current take profit level.
- HedgingCycleInProgress: Indicates whether a hedging cycle is in progress.

## Initialization Function

The OnInit() function is called during the Expert Advisor initialization. It retrieves the current account balance and initializes the LotSize variable.

## Start Function

The OnStart() function is called when the Expert Advisor starts trading. It performs manual analysis of technical indicators, calculates the optimal lot size based on the risk percentage and account balance, and opens an initial trade with the calculated lot size. It also sets the initial stop loss and take profit levels and initializes the HedgingCycleInProgress variable.

## Tick Function

The OnTick() function is called on every tick of the market. It checks if a hedging cycle is in progress. If a cycle is in progress, it checks if the current position is profitable enough to close the cycle. If so, it closes all open orders in the cycle and sets the HedgingCycleInProgress variable to false. If a cycle is not in progress, it checks if the current position is at a loss. If so, it calculates new stop loss and take profit levels for the hedging cycle and opens a hedging order with the same lot size as the initial trade. It sets the HedgingCycleInProgress variable to true.

## Deinitialization Function

The OnDeinit() function is called when the Expert Advisor is being deinitialized. It closes all open orders before deinitialization.

Please note that ForexRobotEasy is not the official developer of this product. We are only providing a sample code that can work as described in this product. To find the official developer of this product, please refer to MQL5.

For detailed reviews and trading results of this product, please visit [Forex Robot Easy - SmartHedging Review](https://forexroboteasy.com/forex-robot-review/smarthedging-review-profit-boosting-forex-tool-for-mt4/).
