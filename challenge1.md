## Stock Quantity Validation
 
 One assumption we made on the base exercise was that we won't have any operations in which the investor will sell more stocks than they have. 
 For this extension, you will need to output an error message when the investor inputs an operation that tries to sell more stocks than they have.
 
Input #1
 [{"operation":"buy", "unit-cost":10, "quantity": 10000}, {"operation":"sell", "unit-cost":20, "quantity": 11000}]
 
 Output #1
 [{"tax":0}, {"error":"Can't sell more stocks than you have"}]
 
 Input #2
 [{"operation":"buy", "unit-cost": 10, "quantity": 10000}, {"operation":"sell", "unit-cost":20, "quantity": 11000}, {"operation":"sell", "unit-cost": 20, "quantity": 5000}]
 
 Output #2
 [{"tax":0}, {"error":"Can't sell more stocks than you have"}, {"tax":10000}]
