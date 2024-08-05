### brute force search - substring search
ブルートフォース検索 - 部分文字列検索


```javascript

function bruteForceSearch(text, pattern){
  let result = []

  for(let i = 0; i <= text.length - pattern.length; i++){
    if(text.substring(i, i + pattern.length) == pattern) {
      result.push(i)
    }
  }
  
  return result
}

let text = "これはテストテキストです。テストは大事です。" // 22
let pattern = "テスト" // 3

console.log(bruteForceSearch(text, pattern))
// [3, 13]

```
