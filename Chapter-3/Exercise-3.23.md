# Exercise 3.23

Explain the bit pattern each of the following `bitset` objects contains:

(a) `bitset<64> bitvec(32);`
(b) `bitset<32> bv(1010101);`
(c) `string bstr; cin >> bstr; bitset<8> bv(bstr);`

**Answer**:

(a) `0 ...(56 zeros)... 0100000`
(b) `00000000000011110110100110110101`
(c) contains the first 8 elements of the `string bstr`