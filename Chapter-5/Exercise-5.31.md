# Exercise 5.31

Given the variable definition on page 180, explain what conversions take place when evaluating the following expressions:

(a) `if (fval)`
(b) `dval = fval + ival;`
(c) `dval + ival + cval;`

Remember that you may need to consider associativity of the operators in order to determine the answer in the case of expressions involving more than one operator.

**Answer**:

```cpp
bool flag;
short sval;
int ival;
long lval;
float fval;
char cval;
unsigned short usval;
unsigned int uival;
unsigned long ulval;
double dval;
```

(a) `if (fval)`, if `fval` is 0, it is converted to `false`, otherwise `true`;
(b) `dval = fval + ival;`, `ival` converted to `float`, then the result converted to `double`;
(c) `dval + ival + cval;`, `ival` converted to `double`, `cval` converted to `int` then to `double`.