
7*n
```javascript
function multipleOf7(n) {
  if(n <= 0) {
    return 0
  }

  return multipleOf7(n - 1) + 7
}
```

m*n
```javascript
function multiply(m, n) {
  if(n <= 0) return 0

  return multiply(m, n - 1) + m
}
```

lengthOfString
```javascript
function lengthOfString(s) {
  if(s === "") return 0

  return lengthOfString(s.slice(0, -1)) + 1
}
```

総和
```javascript
function summation(n) {
  if(n <= 0) return 0

  return summation(n - 1) + n
}

// f(0) = 0
// f(n) = f(n - 1) + n
```

階乗
```javascript
function factorial(n) {
  if(n <= 0) return 1

  return factorial(n - 1) * n
}

// f(0) = 0
// f(n) = f(n - 1) * n
```

2乗の総和
```javascript
function squareSummation(n) {
  if(n <= 0) return 0

  return squareSummation(n - 1) + n**2
}

// f(0) = 0
// f(n) = f(n - 1) + n**
```

文字列の合体
```javascript
function mergeString(s1, s2) {
  if(s1 === "") return ""

  return s1[0] + s2[0] + mergeString(s1.slice(1), s2.slice(1))
}

// f("") = ""
// f(s1, s2) = s1[0] + s2[0] + f(s1.slice(1), s2.slice(1))
```

偶奇の入れ替え
```javascript
function swapPosition(s) {
  if(s.length <= 1) return s

  return s[1] + s[0] + f(s.slice(2))
}

// f("") = ""
// f("a") = "a"
// f(s) = s[1] + s[0] + f(s.slice(2))
```

掛け算
```javascript
function producct(x, y) {
  if(y == 0) return 0

  if(y > 0) return product(x, y - 1) + x
  else return product(x, y + 1) - x
}

// f(x, 0) = 0
// f(x, y) = f(x, y - 1) + x
// f(x, -y) = f(x, y + 1) - x
```

共通の接頭辞
```javascript
function commonPrefix(s1, s2) {
  if(s1 == "" || s2 == "" || s1[0] !== s2[0]) return ""

  return s1[0] + commonPrefix(s1.slice(1), s2.slice(1))
}

// f(s1 = "" | s2 = "" || s1[]) = ""
// f(s1, s2) = s1[0] + f(s1.slice(1), s2.slice(1)) 
```

パスカルの三角形
```javascript
function numberOfDots(x){
    if(x == 0) return 0
    return numberOfDots(x-1) + x
}

// f(0) = 0
// f(n) = numberOfDots(n - 1) + n
```

正方形の合計面積
```javascript
function totalSquareArea(x) {
  if(x == 1) return 1

  return totalSquareArea(x - 1) + x**2 * x
}

// f(1) = 1
// f(n) = f(n - 1) + n**2 * n
```

羊を数える
```javascript
function sheeps(count) {
  if(count <= 0) return 0

  return sheeps(count - 1) + count + " sheep ~ "
}

// f(0) = ""
// f(n) = f(n - 1) + n + " sheep ~ " 
```

文字列の逆表示
```javascript
function reverseString(s) {
  if(s.length == 0) return ""

  return reverseString(s.slice(1)) + s[0]
}

// s.length = 0, f(s) = ""
// s.length > 0, f(s) = f(s.slice(1)) + s[0]
```

最大公約数
```javascript
function gcd(m, n) {
  if(n == 0) return m

  return gcd(n, m % n)
}

// n = 0, gcd(m, n) = m
// n > 0, gcd(m, n) = gcd(n, m % n)
```

kで割り続ける
```javascript
function countDivisibleByK(n,k){
  if(n % k != 0) return 0

  return countDivisibleByK(n / k, k) + 1
}

// n % k != 0, f(n, k) = 0
// n % k = 0, f(n, k) = f(n / k, k) + 1
```

仮想通貨
```javascript
function maximumPeople(x,y){
  if(y == 0) return x

  return maximumPeople(y, x % y)
}

// y = 0, maximumPeople(x, y) = x
// y > 0, maximumPeople(x, y) = maximumPeople(y, x % y)
```

3つの最大公約数
```javascript
function threeGCD(x, y, z) {
  return gcd(gcd(x, y), z)
}
  
function gcd(x, y) {
  if(y == 0) return x
  return gcd(y, x % y)
}

// y = 0, gcd(x, y) = x 
// y > 0, f(x, y) = f(y, x % y)
```

既約分数
```javascript
function irreducibleFraction(x, y) {
  let z = gcd(x, y)
  return y / z == 1 ? `${x / z}` : `${x / z}/${y / z}`
}
  
function gcd(x, y) {
  if(y == 0) return x
  return gcd(y, x % y)
}

// y = 0, gcd(x, y) = x
// y > 0, gcd(x, y) = gcd(y, x % y)
```

購入できる最大のパンの個数
```javascript
function maxBread(money, price, sticker) {
    let bread = Math.floor(money / price)
    bread += stickerForBread(sticker, bread)
    return bread
}
  
function stickerForBread(required, current) {
    if(current < required) return 0
    const bread = Math.floor(current / required)
    return stickerForBread(required, current % required + bread) + bread
}

// current < required, stickerForBread(required, current) = 0
// current >= required, stickerForBread(required, current) = stickerForBread(required, current % required + Math.floor(current / required)) + Math.floor(current / required)
```

文字列の圧縮
```javascript
function stringCompression(s) {
  if(s == "") return ""
  let count = stringCount(s, s[0])
  let compressedPart  = count > 1 ? s[0] + count : s[0]
  return compressedPart + stringCompression(s.slice(count))
}

// s = "", f(s) = ""
// s = "...", f(s) = f(s) = s[0] + stringCount(s, s[0]) + f(s.slice(stringCount(s, s[0])))
  
function stringCount(s, value) {
  if(s[0] != value) return 0
  return stringCount(s.slice(1), value) + 1
}

// s[0] != value, f(s) = 0
// s[0] = value, f(s) = f(s.slice(1)) + 1
```

整数上の平方根
```javascript
function intSquareRoot(n) {
  return intSquareRootHelper(n, 1)
}

function intSquareRootHelper(n, guess) {
  if(guess**2 > n) return guess - 1
  return intSquareRootHelper(n, guess + 1)
}

// guess**2 > n, f(n, guess) = guess - 1
// guess**2 < n, f(n, guess) = f(n, guess + 1)
```
