Similarly to bubble sort selection sort  have a time complexity of  `O(n^2)` as we are using nested loops. However if the data is nearly sorted the time complexity can decrease.
We place smaller values first and then work up. Its essentially opposite of bubble sort  but we only swap once a iteration.
we swap  the first position with the smallest value and move up.
example `[5,3,4,1,2]`
first iteration: `[ 1,3,4,5,2]`
second iteration: `[1,2,4,5,3]`
third iteration: `[1,2,3,5,4]`
fourth iteration: `[1,2,3,4,5]`

```
function selectionSort(arr){
     
    for(let i = 0; i < arr.length; i++){
        let lowest = i
        for (let j = i + 1; j < arr.length; j++){
            if(arr[j] < arr[lowest]){
                //swap
                lowest = j
            }
        }
         let swap = arr[i]
         arr[i] = arr[lowest]
         arr[lowest] = swap
    }
    return arr;
}

selectionSort([38,22,33,28,11])
```