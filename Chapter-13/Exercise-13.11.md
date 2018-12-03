# Exercise 13.11

What is a destructor? What does the synthesized destructor do? When is a destructor synthesized? When must a class define its own destructor?

**Answer**:

**What is a destructor?** The destructor is a special member function that can be used to do whatever resource de-allocation is needed. It serves as the complement to the constructors of the class.

**What does the synthesized destructor do?** The synthesized destructor destroys each non`static` member in the reverse order from that in which the object was created. In consequence, it destroys the members in reverse order from which they are declared in the class.

**When is a destructor synthesized?** Anytime.

**When must a class define its own destructor?** Destructors are needed only if there is work for them to do. Ordinarily they are used to relinquish resources acquired in the constructor or during the lifetime of the object.