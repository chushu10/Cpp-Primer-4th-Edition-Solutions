# Exercise 5.28

With the exception of the logical AND and OR, the order of evaluation of the binary operators is left undefined to permit the compiler freedom to provide an optimal implementation. The trade-off is between an efficient implementation and a potential pitfall in the use of the language by the programmer. Do you consider that an acceptable trade-off? Why or why not?

**Answer**:

Not acceptable. Because the program should behave universally to avoid any possible errors. If the code is efficient in one machine and error in the other, it is definitely not acceptable.