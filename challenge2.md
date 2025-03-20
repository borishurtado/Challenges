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
