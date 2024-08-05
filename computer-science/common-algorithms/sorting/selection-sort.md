### selection sort

未ソートの要素内から最小値または最大値を選択し、未ソート内の先頭の要素と置換を行います。

```
let arr = [64, 34, 25, 12, 22, 11, 90]

function selectionSort(arr){
	let l = arr.length

  for(let i = 0; i < l - 1; i++){
    let index = i
    
    for(let j = i+1; j < l; j++){
      if(arr[index] < arr[j]) index = j
    }
    
    let temp = arr[i]
    arr[i] = arr[index]
    arr[index] = temp
  }
}

selectionSort(arr)
console.log(arr)
// [90, 64, 34, 25, 22, 12, 11]
```
