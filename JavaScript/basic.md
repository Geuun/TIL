### JavaScript basic

---


```js
// 주사위 게임 ( 랜덤 인트 )

function randint(maxnum) {
    var dice = Math.floor(Math.random() * maxnum) + 1;
    document.write(dice);
}

randint(6);
```

---

```js
// 매개변수 n이 소수라면 true를, 소수가 아니라면 false를 반환
function isPrime(n){
    var divisor = 2;
    if (n == 1){
        return false;
    }
    while (n > divisor){
        if (n % divisor ==0) {
            return false;
        } else {
            divisor++;
        }
    }
    return true;
}

/* ---------------- 검사용 ------------------- */
for(var i = 1; i <= 10; i++) {
    document.writeln(i, isPrime(i));
}
```

```js
/* 문자열 거꾸로 출력하기 */
function reverse(str){

    var reverStr = "";

    for(var i = str.length-1; i >= 0 ; i--) {
        reverStr = reverStr + str.charAt(i)
    }

    return reverStr;
}

document.write(reverse("Nice to meet you"));
```

```js
/* 구구단 함수 만들기 */
function timesTable(n) {
    for( var i = 1 ; i < 10 ; i++) {
        document.writeln(`${n} x ${i} = ${n * i} <br>`)
    }
}

timesTable(2); // 2단만 출력
timesTable(3); // 3단만 출력
```

```js
/* 2중 For문을 이용해서 9x9 까지 출력 */
for (var n = 1; n < 10 ; n++) {
    for ( var i = 1 ; i < 10 ; i++) {
        document.writeln(`${n} x ${i} = ${n * i} <br>`);
    }
}
```

---

## js review

---
### 변수선언

let & const

- let : 변수는 선언하지만 값을 바꿀수 도 있을 때
- const : 변수와 값을 바꿀 일이 없을 때

코드에서 무슨 일이 일어나고 있는지 확실히 하기위해 **const**를 사용하는게 좋음

### 화살표 함수

function 구문 없이 함수를 선언할 수 있음
따라서 아래의 두 함수는 같은 기능
```js
const demo = function(x, y, z) {
    return x + y + z
};

const demo = (x, y, z) => {
    return x + y + z
};
```

