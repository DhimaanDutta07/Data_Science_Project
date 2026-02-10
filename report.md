Primetrade ai assignment
Trader performance vs market sentiment

Objective
Study how bitcoin fear and greed sentiment relates to trader behavior and performance on hyperliquid
Focus on actionable insights for smarter trading

Datasets used
Fear greed index dataset
Columns date classification value

Hyperliquid historical trader dataset
Columns account coin execution price size usd side timestamp closed pnl fee trade id

Important note about dataset
The hyperliquid dataset contains trades for only a small number of active dates
Because of this the analysis is cross sectional across sentiment regimes
Not a full time series across all calendar days

Part A Data preparation

Steps performed
Loaded both datasets
Checked rows columns missing values duplicates
Converted hyperliquid timestamp from epoch milliseconds into daily date
Converted sentiment date into daily date
Created sentiment bucket fear greed neutral
Merged both datasets by daily date using inner join

Key metrics created per trader per day
Trades per day
Volume usd per day
Average trade size usd
Long ratio percent buy trades
Daily pnl sum of closed pnl
Daily fees
Win rate percent of trades with positive closed pnl

Part B Analysis

Question 1
Does performance differ between fear vs greed days

Evidence used
Performance summary table by sentiment
Pnl distribution chart by sentiment
Tail loss table using bottom ten percent pnl as drawdown proxy

Findings
Fear days show different pnl distribution compared to greed days
Median pnl and percent profitable trader days changes by sentiment
Tail losses show risk differences across sentiment regimes

Question 2
Do traders change behavior based on sentiment

Evidence used
Behavior summary table by sentiment
Mean trades chart by sentiment
Mean long ratio chart by sentiment

Findings
Trade frequency changes between fear and greed days
Average trade size and daily volume changes by sentiment
Directional bias measured by long ratio shifts across sentiment regimes

Question 3
Trader segments

Segments created
Segment 1 frequent vs infrequent traders using top quantile of trades per day
Segment 2 high volume vs low volume traders using top quantile of volume usd per day
Segment 3 consistent vs inconsistent traders using ratio of profitable days per trader

Evidence used
Segment performance tables by sentiment
Segment mean pnl chart for activity segments

Findings
Frequent traders behave differently than infrequent traders under fear and greed
High volume traders show stronger pnl swings and higher risk on some sentiment regimes
Consistent traders show more stable performance and better profitability across regimes

Part C Actionable strategy rules

Rule 1 Risk control on fear days
If tail losses are worse on fear days reduce trade size and reduce trading frequency for frequent and high volume traders
Exception allow consistent traders to continue with controlled frequency

Rule 2 Controlled scaling on greed days
If median pnl is higher on greed days allow consistent traders to increase frequency slightly
Keep infrequent and low volume traders cautious to avoid noise trades and overtrading

Limitations
Only a small number of active trading dates are available in the trader dataset
Leverage data is not present so leverage based segmentation could not be performed
Results should be treated as directional insights and not final production strategy

Deliverables
Notebook includes full workflow
Data preparation metrics analysis charts and outputs saved in figures and outputs folders
