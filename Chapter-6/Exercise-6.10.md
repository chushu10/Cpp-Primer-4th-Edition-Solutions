# Exercise 6.10

Each of the programs in the highlighted text on page 206 contains a common programming error. Identify and correct each error.

**Answer**:

(a)

```cpp
switch (ival) {
    case 'a': aCnt++; // no break
    case 'e': eCnt++; // no break
    default: iouCnt++;
}
```

(b)

```cpp
switch (ival) {
    case 1: // should have braces when declaring ix
        int ix = get_value();
        ivec[ ix ] = ival;
        break;
    default:
        ix = ivec.size()-1; // ix not in this scope
        ivec[ ix ] = ival
}
```

(c)

```cpp
switch (ival) {
    case 1, 3, 5, 7, 9: // should use seperate cases
        oddcnt++;
        break;
    case 2, 4, 6, 8, 10: // should use seperate cases
        evencnt++;
        break;
}
```

(d)

```cpp
int ival =512 jval=1024, kval=4096; // missing ,
int bufsize;
// ...
switch(swt) {
    case ival: // can't use variable in case
        bufsize = ival * sizeof(int);
        break;
    case jval: // can't use variable in case
        bufsize = jval * sizeof(int);
        break;
    case kval:
        bufsize = kval * sizeof(int);
        break;
}
```