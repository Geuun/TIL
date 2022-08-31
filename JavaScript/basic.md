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

그리고 화살표 함수의 변수들은 node code의 전역을 참고한다.  
아래 코드 참고

```js
const person = {
    name : 'Geun',
    age : 27,
    greet: () => {
        console.log('Hi, I am' + this.name)
    }
};

person.greet();

// -> Hi, I am undefined

const person = {
    name : 'geun',
    age : 27,
    greet: function() {
        console.log('Hi, I am' + this.name);
    }
};

person.greet()

// -> Hi, I am geun

const person = {
    name : 'geun',
    age : 27,
    greet() {
        console.log('Hi, I am' + this.name);
    }
};

// -> Hi, I am geun
```

### 배열(array)

```js
const hobbies = ['Sports', 'Cooking'];

for (let hobby of hobbies) {
    console.log(hobby);
}
```

### map 함수

ECMA 설명
- 주어진 배열의 값들을 오름차순으로 접근해 callbackfn을 통해 새로운 값을 정의하고 신규 배열을 만들어 반환

코드로 이해해보자.
```js
const numbers = [1, 2, 3, 4, 5];
const squared = numbers.map(numbers => number * number);

console.log(numbers);
// -> [1, 2, 3, 4, 5]
console.log(squared);
// -> [1, 4, 9, 16, 25]
```

만약 for 구문을 사용해서 map 함수를 구현한다면 아래와 같다.

```js
const numbers = [1, 2, 3, 4, 5]
const squared = [];

for (i = 0; i < numbers.length; i++) [
    squared.push(numbers[i] * numbers[i]);
];

console.log(squared);
// -> [1, 4, 5, 16, 25]
```

### Spread

```js
const hobbies = ['Sports', 'Cooking'];
const copiedArrary = [hobbies];
console.log(copiedArray);
//-> [['Sports', 'Cooking']]

const copiedArray = [...hobbies];
cosole.log(copiedArray);
//-> ['Sport','Cooking']
```

### Rest

```js
const toArray = (arg1, arg2, arg3) => {
    return [arg1, arg2, arg3];
};

console.log
```
위 함수는 전혀 유연하지 않으므로 인자를 추가하려면 코드 전체를 수정해야한다.  
이 때 사용하는게 Rest

```js
const toArray = (...args) => {
    return args;
};

console.log(toArray(1, 2, 3, 4));
// -> [1, 2, 3, 4]
```

### Rest / Spread 차이점

- 배열이나 객체에서 원소나 속성을 추출하는 데 사용한다면 **Spread**
- 인수 목록이나 함수에서 여러 인수를 하나의 배열로 묶는데 사용한다면 **Rest**


### Destructuring

객체 (object) 의 경우
```js
const person = {
    name : 'geun',
    age : 27,
    country : 'Republic of korea',
}

const item = {
    name : 'Macbook',
    category : 'Laptop',
    value : 100,
}

const printName = ({ name }) => {
    console.log(name);
}

printName(person);
// -> geun

printName(item);
// -> Macbook


var {name, age} = person;
console.log(name, age);
// -> geun 27

var {name, value} = item;
console.log(name, value);
// -> Macbook 100

```

배열 (array)의 경우
- 불러올 이름을 맘대로 지정가능 인덱스를 기반으로 불러오기 때문

```js
const hobbies = ['Sports', 'Cooking'];
const [hobby1, hobby2] = hobbies;
console.log(hobby1, hobby2);
// -> Sports Cooking
```

### 비동기 코드

```js
setTimeout(() => {
    console.log('Timer is done!')
}, 2000);

console.log('Hello!')
console.log('Hi!')

/** Hello!
 * Hi!
 * Timer is done!
 */
```
코드의 출력을 보면 알 수 있듯이 Node.js 와 JavaScript는 비동기적으로 실행됨을 알 수 있다.

- 콜백 함수로 setTimeout 안의 내용을 인식해 모든 동기화 테스크가 완료된 후 비동기 테스크를 답신하게 된다.
- callback의 늪을 조심하자..!!!


### new연산자와 생성자 함수

1. 함수의 이름의 첫 글자는 대문자로 시작
2. 반드시 `new` 연산자를 붙여 실행

```js
function User(name) {
    this.name = name;
    this.isAdmin = false;
}

let user = new User('보라')

console.log(user.name); 
// -> 보라
console.log(user.isAdmin);
// -> false
```


### 프로미스 (Todo : 이해가 더 필요)

```js
const fetchData = callback => {
    const promise = new Promise((resolve, reject) => {
        setTimeout(() => {
            callback('Done!')
        },1500);
    });
};

setTimeout(() => {
    console.log('Timer is done!');
    fetchData(text => {
        console.log(text);
    });
}, 2000);

console.log('Hello!');
console.log('Hi!');
```
