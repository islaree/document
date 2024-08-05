### brute force search - substring search


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
