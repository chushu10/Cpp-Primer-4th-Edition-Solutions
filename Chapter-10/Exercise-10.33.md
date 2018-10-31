# Exercise 10.33

Why doesn't the `TextQuery::text_line` function check whether its argument is negative?

**Answer**:

Because the parameter with type `line_no` is always starting from 0, it will never be negative in this scenario. However, forgetting to do non-negative check is a common mistakes made by many programmers.