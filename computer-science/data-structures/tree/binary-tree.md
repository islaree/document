### binary tree

各ノードが最大で2つの子ノードを持つ木構造のデータ構造です。

```javascript
class TreeNode {
  constoructor(value, left = null, right = null){
    this.value = value
    this.left = left
    this.right = right
  }
}

let root = new TreeNode(10)
```

