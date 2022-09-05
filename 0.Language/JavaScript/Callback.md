## Callback function

### 콜백함수란?

- 콜백함수(Callback Function)이란 파라미터로 함수를 전달받아 함수의 내부에서 실행하는 함수이다.

코드로 예를들어보면, 아래와 같다

```js
const number = [1, 2, 3, 4, 5];

number.forEach(x => {
    console.log(x * 2);
});

>2
>4
>6
>8
>10
```

위의 코드의 forEach 함수의 경우 함수 안에 익명의 함수를 넣어서 forEach 함수를 동작시킨다.

