# Tips JavaScript

### Personal sort depending a function
```javascript
ranges.sort(function(a, b) {
    return a[1] - b[1];
});
```

### ASCII code <-> character
```javascript
// ASCII -> character
"\n".charCodeAt(0)
// Character -> ASCII
char c = '1';
int i = c - '0'; // i is now equal to 1, not '1'
```

### Comparison
`===` 	equal value and equal type  
`==` 	equal to    (true for int and string)

## Time

### Return the number of milliseconds since 1970/01/01
```javascript
(new Date()).getTime();
```

## Random

### Return a random number between 1 and 100
```javascript
Math.floor((Math.random() * 100) + 1);
```

## Object

### Initiate object
```javascript
obj = {
  a:1,
  b:"coool",
  c:{x:1, y,2}
};
```

## Array
```javascript
// Window of size 2 of each value of the array
array.reduce

array.map

// Get subarray from beginning to end-1
array.slice(1, 4)

//
splice( pos, n )

// Remove last item and return it
array.pop()
// Remove first item and return it
array.shift()
```

#### Fill an array with a value Y, X times
```javascript
(new Array(X)).join(Y)
(new Array(X)).fill(Y)
```

#### Construct array 2D
```javascript
for (let i = 0 ; i < words.length ; i++) arrays.push([i])
```

### Apply a function on each element of an array
```javascript
a.forEach(function(element) {
    console.log(element);
});
```
