### tail recursion

再帰呼び出しが最後の操作であり、再帰呼び出しの後に何も処理が続かない場合

```
function recursion(n, sum = 0){
	if(n == 0){
		return sum
	}
  
  return recursion(n - 1, sum + n)
}

console.log(recursion(5))
// 15
```
