### bubble sort

1. 隣接要素の比較：リストの先頭から初めて、隣接する要素を比較します。
2. 交換：比較した要素の順序が逆であれば、これらの要素を交換します。
3. 次の要素に進む：リストの末尾まで進みます。
4. 繰り返し：リストのすべての要素がソートされるまで、上記の手順を繰り返します。

```
let arr = [64, 34, 25, 12, 22, 11, 90]

function bubbleSort(arr) {
  for(let i = 0; i < arr.length - 1; i++){
    for(let j = 0; j < arr.length - i - 1; j++){
      if(arr[j] < arr[j+1]){
        let temp = arr[j]
        arr[j] = arr[j+1]
        arr[j+1] = temp
      }
    }
  }
}

bubbleSort(arr)
console.log(arr)
// [90, 64, 34, 25, 22, 12, 11]
```
