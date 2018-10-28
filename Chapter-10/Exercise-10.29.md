# Exercise 10.29

Explain the meaning of the operand `pos.first->second` used in the output expression of the final program in this section.

**Answer**:

As the associativity order of `.` operator is higher than `->`, so that `pos.first->second` means get the `first` member of `pos` then apply `->` operator on that member to get its `second` member.

However, `(pos.first)->second` may be more precise and easier to understand.