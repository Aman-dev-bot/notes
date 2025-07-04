```
function merge(arr1, arr2) {

  let arr = [];
  let i = 0;
  let j = 0;
  while (i < arr1.length && j < arr2.length) {
    if (arr2[j] > arr1[i]) {
      arr.push(arr1[i]);
      i++;
    } else {
      arr.push(arr2[j]);
      j++;
    }
  }
  while (i < arr1.length) {
    arr.push(arr1[i]);
    i++;
  }
  while (j < arr2.length) {
    arr.push(arr2[j]);
    j++;
  }
  return arr;
``` 
`this need inputs as a sorted array of 0 or 1`

```
function mergeSort(arr){
let  middle = Math.floor(arr.length / 2)
let left = mergeSort(arr.slice(0,mid))
let right = mergeSort(arr.slice(mid))
merge(left,right)
}
``` 
