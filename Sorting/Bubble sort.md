Bubble sort have a time complexity of  `O(n^2)` as we are using nested loops. However if the data is nearly sorted the time complexity can decrease.
It works by bubbling  the largest value to the end of the array and then looping again and putting the second largest value in second last position. The process continues until the array is sorted
example: `[23,5,55,3,4,7]`
first iteration: `[5,23,3,4,7,55]`
second iteration: `[5,3,4,7,23,55]`
third iteration: `[3,4,5,3,23,55]`

```
function bubbleSort(arr) {
  // isSwap is implemted so if the array is sorted before all the iterations are  
  // done the login should stop.
  let isSwap;
  for (let i = arr.length; i > 0; i--) {
    let isSwap = true;
    for (let j = 0; j < i - 1; j++) {
      // if the if block does not run we cannot set isSwap to false which
      // isSwap is set to true which breaks the loop.
      if (arr[j] > arr[j + 1]) {
        // swapping logic
        let swap = arr[j];
        arr[j] = arr[j + 1];
        arr[j + 1] = swap;
        let isSwap = false;
      }
    }
    if (isSwap) break;
  }
  return arr;
}

bubbleSort([5, 55, 23, 47]);
```
