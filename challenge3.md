## Multiple Stocks
 Now we should consider multiple tickers, so the input for an operation will also contain a new information called "ticker" that will be an identifier of which asset you're selling. The profit calculation (through weighted-average price) and quantity validation (if implemented) on selling should also consider the ticker.
 
 When you sell at a loss, you should use the loss from one ticker toward any other ticker.
 
 Input #1
 [{"operation":"buy", "unit-cost":10, "quantity": 10000, "ticker":"AAPL"},
 {"operation":"buy", "unit-cost":15, "quantity": 10000, "ticker":"MANU"}, {"operation":"sell", "unit-cost":20, "quantity": 10000, "ticker":"AAPL"},
 {"operation":"sell", "unit-cost":30, "quantity": 10000, "ticker":"MANU"}]
 
 Output #1
 [{"tax":0}, {"tax":0}, {"tax":20000}, {"tax":30000}]
 
 Input #2
 
 [{"operation":"buy", "unit-cost":10, "quantity": 10000, "ticker":"AAPL"},
 {"operation":"buy", "unit-cost":15, "quantity": 10000, "ticker":"MANU"}, 
 {"operation":"sell", "unit-cost":5, "quantity": 10000, "ticker":"AAPL"},
 {"operation":"sell", "unit-cost":30, "quantity": 10000, "ticker":"MANU"}]
 
 Output #2
 [{"tax":0}, {"tax":0}, {"tax":0}, {"tax":20000}]
 
 Input #3
 [{"operation":"buy", "unit-cost":10, "quantity": 10000, "ticker":"AAPL"},
 {"operation":"buy", "unit-cost":15, "quantity": 10000, "ticker":"MANU"},
 {"operation":"sell", "unit-cost":30, "quantity": 10000, "ticker":"MANU"},
 {"operation":"sell", "unit-cost":5, "quantity": 10000, "ticker":"AAPL"}]
 
 Output #3
 [{"tax":0}, {"tax":0}, {"tax":30000}, {"tax":0}]
