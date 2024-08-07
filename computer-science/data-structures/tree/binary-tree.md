### binary tree - 二分木

各ノードが最大で2つの子ノードを持つ木構造のデータ構造です。

```mathematica
  1
 / \
2   3
```

```javascript
class Node {
  constructor(data, left = null, right = null){
    this.data = data
    this.left = left
    this.right = right
  }
}

const rootNode = new Node(1)
const leftNode = new Node(2)
const rightNode = new Node(3)

rootNode.left = leftNode
rootNode.right = rightNode

console.log(rootNode)
```
result
```javascript

{
  data: 1,
  left: {
    data: 2,
    left: null,
    right: null
  },
  right: {
    data: 3,
    left: null,
    right: null
  }
}

```

