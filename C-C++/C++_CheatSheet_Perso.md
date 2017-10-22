# Core

## Vector

### Adding a vector to another one
```c++
a.insert(std::end(a), std::begin(b), std::end(b));
a.insert(a.end(), b.begin(), b.end());
```

### Delete something in vector
```c++
// erase the 6th element
myvector.erase (myvector.begin()+5);
```

### erase the first 3 elements
```c++
myvector.erase (myvector.begin(),myvector.begin()+3);
```

## Print

### Align print
```c++
/** function and line with all example
 * width: total space (count the separator)
 * separator: put at the end of the block
 * t: object to print
 * left: align place
*/
template<typename T> void printElement(T t, const int& width)
{
    cout << left << setw(width) << setfill(separator) << t;
}
```
