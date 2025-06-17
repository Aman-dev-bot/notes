By default JavaScript uses `.sort()` method.
The default sort order is ascending, built upon converting the elements into strings, then comparing their sequences of UTF-16 code unit values.

```
["Let's", "Learn", "Coding"].sort()

// it returns ['Coding', 'Learn', "Let's"]

``` 

However, the default sort does not work with numbers as they are also converted into strings.

```
[1,3,8,23,12,9,55].sort()

// expected [1, 3, 8, 9, 12, 23, 55]
// returns  [1, 12, 23, 3, 55, 8, 9]

``` 

To sort properly in JavaScript we need to provide a callback function to `.sort()`

```
[1,3,8,23,12,9,55].sort((a,b)=> a-b)

// returns [1, 3, 8, 9, 12, 23, 55]
```

- If the function is `a-b` it returns in ascending order.
- If the function is `b-a` it returns in descending order.
- If the sum of the inputs in function is `0` then it has the same value.
- It also works for strings. This method return by the `.length()` of the string.

```
["a","abcd","ab","abc"].sort((a,b)=> a.length - b.length)

// returns ['a', 'ab', 'abc', 'abcd']
``` 

