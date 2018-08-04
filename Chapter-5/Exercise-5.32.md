# Exercise 5.32

Given the following set of definitions:

```cpp
char cval;
int ival;
unsigned int ui;
float fval;
double dval;
```

identify the implicit type conversions, if any, taking place:

(a) `cval = 'a' + 3;`
(b) `fval = ui - ival * 1.0;`
(c) `dval = ui * fval;`
(d) `cval = ival + fval + dval;`

**Answer**:

(a) `cval = 'a' + 3;`, `'a'` being converted to int, then `'a' + 3` being converted to `char`;
(b) `fval = ui - ival * 1.0;`, * operator has higher precedence, so `ival` being converted to `double` first, then `ui` beging converted to `double`;
(c) `dval = ui * fval;`, `ui` being converted to `float`, then `ui * fval` being converted to `double`;
(d) `cval = ival + fval + dval;`, + operator is calculated from left to right, so `ival` being converted to `float` first, then the result being converted to `double`, then the final result being converted to `char`.