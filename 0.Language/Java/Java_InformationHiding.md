## 정보 은닉(Information hiding)

-   객체 지향 프로그래밍에서 접근 가능한 최소한의 정보를 오픈함으로써 객체의 오류를 방지하여 클라이언트가 객체를 더 효율적으로 활용할 수 있도록 하는 기법

### 정보은닉의 필요성

<img width="506" alt="Untitled" src="https://user-images.githubusercontent.com/89567475/193263881-49645e9e-7345-428b-adb5-157d22e8c420.png">

-   변수에 다이렉트로 접근하지 않도록 문법적으로 제한해준다.
    메소드를 통해서 값을 설정하도록 정보를 보호해주는 것.
    -   `private double rad = 0;` 으로 설정해주면 -4.5로 설정되지 않을 것이다.

<img width="510" alt="Untitled1" src="https://user-images.githubusercontent.com/89567475/193263889-b4dac932-2cfe-44d8-933e-e900f5f24b10.png">

### 실무에서는..!

1. 모든 변수를 private으로 선언한다.\_
2. 모든 변수에 대해서 getter, setter 함수를 만들어서 값을 읽고 쓴다.\_

-   getter, setter 함수 만들기

        소스코드에서 마우스 우클릭 > source > Generate Getters and Setters… > getter, setter 만들 변수들 체크하고 generate 버튼
