# Exercise 14.9

Describe the behavior of the `Sales_item` input operator if given the following input:

(a) 0-201-99999-9 10 24.95
(b) 10 24.95 0-210-99999-9

**Answer**:

Given input (a) will be ok, because the input operator of `Sales_item` reads `isbn` first, then `units_sold`, then `price`. However, given input (b), the input operator should set the condition state of `ostream` to `failbit`, since `10` is not the correct format of `isbn`.