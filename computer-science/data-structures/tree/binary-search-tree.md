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
