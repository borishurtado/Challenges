# Challenges
## Stock Quantity Validation

One assumption we made on the base exercise was that we won't have any operations in which the investor will sell more stocks than they have. For this extension, you will need to output an error message when the investor inputs an operation that tries to sell more stocks than they have.

Input #1
[{"operation":"buy", "unit-cost":10, "quantity": 10000}, {"operation":"sell", "unit-cost":20, "quantity": 11000}]

Output #1
[{"tax":0}, {"error":"Can't sell more stocks than you have"}]

Input #2
[{"operation":"buy", "unit-cost": 10, "quantity": 10000}, {"operation":"sell", "unit-cost":20, "quantity": 11000}, {"operation":"sell", "unit-cost": 20, "quantity": 5000}]

Output #2
[{"tax":0}, {"error":"Can't sell more stocks than you have"}, {"tax":10000}]


## Stock Quantity Error Limit
(If the stock quantity validation is quickly implemented or want more insights from the candidate)
After validating the stock quantity, we will check if the investor tries to perform multiple invalid actions consecutively, if such an error happens we block the following operations, even if those are valid.

Input #1
[{"operation":"sell", "unit-cost":20, "quantity": 10000},
{"operation":"sell", "unit-cost":20, "quantity": 10000},
{"operation":"sell", "unit-cost":20, "quantity": 10000},
{"operation":"buy", "unit-cost":10, "quantity": 10000}]

Output #1
[{"error":"Can't sell more stocks than you have"},
{"error":"Can't sell more stocks than you have"},
{"error":"Can't sell more stocks than you have"},
{"error":"Your account is blocked"}]


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

