# Simple Backtesting
## Description
A tool to backtest single factors using SimFin data. Backtest built-in factors and your own!

## Development roadmap
- [x] Price-only tester  
- [x] Cashflow-only tester  
- [x] Balance-only tester  
- [x] Multi-dataset tester
- [ ] Output results in csv 

Although not all multi-dataset testers are included, they can be easily constructed modelling on other multi-dataset testers.

## Disclaimer
The Content is for informational purposes only, you should not construe any such information or other material as legal, tax, investment, financial, or other advice. Nothing contained in this repository constitutes a solicitation, recommendation, endorsement, or offer by the author or any third party service provider to buy or sell any securities or other financial instruments in this or in in any other jurisdiction in which such solicitation or offer would be unlawful under the securities laws of such jurisdiction.  
*You can always send me a tip if you make a profit lol.*

## Tutorial
0. All packages used in this tool are listed in the first cell. `pip install` those packages if you have not installed them yet.
1. Change the root address in the first cell. Expect a ~2.47GB download from SimFin.com. The total size of cached data will reach ~5.34GB.
2. Run the first three cells to initialize. All downloads and temporary data caching happen in this step. It takes ~30mins to finish initialization on the author's old MacBook Pro Early 2015. The data are configured to refresh every 30 days, so running the cells a second time will take significantly less time. You can switch off data reloading altogether by setting *this* to `False`:  
<p align="center"><img width="463" alt="image" src="https://user-images.githubusercontent.com/81217775/121904377-b659f980-cd5b-11eb-89bf-481151eaaebf.png">  

3. The SimFin datasets are officially named: Share Prices, Balance Sheet, Cash Flow, and Income Statement. SimFin also provides a series of signals derived from those datasets: Financial Signals and Growth Signals. In this tool they are called: `prices`, `balances`, `cashflows`, `incomes`, `fin_signals`, and `grow_signals`. Note that in the beginning of second cell there are three variables: `pre`, `mid`, and `post`. They mark the beginning and the end of the "training period" and the "testing period", marked by the prefix `train` and `test` respectively. The periods are fully configurable, but remember to reload the data after changing training or testing periods. It will take less than a minute to reprocess the cached data since no downloads are required. *All datasets are delayed by 12 months on the free edition of SimFin, but the delay does not matter much for backtesting. The author also developed the tool on Free Edition.* 
4. Freely develop your own signals with the datasets. Numerous examples using different datasets are provided within the Notebook. The backtesting tool calculates the signals from the training period and compares the average performance of the top and bottom 100 stocks in the testing period. *The author is trying to figure out how to log the results.*
