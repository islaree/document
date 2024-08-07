### binary search tree

左の子ノードは親ノードよりも小さく、右の子ノードや親ノードよりも大きい構造

```
      12
     /   \
   10     20
  / \     / \
 5  11   16  26
```

```javascript
class Node {
  constructor(data, left = null, right = null){
    this.data = data
    this.left = left
    this.right = right
  }
}

function createBSTHelper(arr, start, end) {
  if(start == end) {
    return new Node(arr[start])
  }

  const mid = Math.floor((start + end) / 2)

  let left = null
  // 左のノードの数が一つの場合には、再帰処理をスキップ
  if(mid - 1 >= start) {
    left = createBSTHelper(arr, start, mid - 1)
  }

  let right = null
  // 右のノードの数が一つの場合には、再帰処理をスキップ
  if(mid + 1 <= end) {
    right = createBSTHelper(arr, mid + 1, end)
  }

  const root = new Node(arr[mid], left, right)
  return root
}

function createBST(arr) {
  if(arr.length == 0) return null
  return createBSTHelper(arr, 0, arr.length - 1)
}

const sortedArr = [1, 2, 3, 4, 5, 6, 7]
```

```mathematica
     4
    / \
  2     6
 / \   / \
1   3 5   7
```

```
function keyExist(key, bst) {
  if(bst == null) return false
  if(bst.data == key) return true

  // keyの値より現在のノードの値が大きければ左側
  if(bst.data > key) return keyExist(key, bst.left)
  else return keyExist(key, bst.right)
}

反復を使用した方法
function keyExist(key, bst) {
  let iterator = bst;
  while(iterator != null) {
    if(iterator.data == key) return iterator
    if(iterator.data > key) iterator = iterator.left
    else iterator = iterator.right
  }

  return false
}
```

検索にかかる時間計算量はO(logN)となる
