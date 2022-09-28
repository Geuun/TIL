# 생성자

## 생성자에 대한 이해

생성자란?

-   객체가 생성될 때에 필드에 초기값을 제공하고 초기화 절차를 실행하는 메소드
-   생성자 = 초기화 라고 이해하면 된다.
-   `new` 뒤에 생성자 함수를 사용한다.
-   생성자 함수 = 객체를 생성할 때 사용한다.

![Untitled](https://user-images.githubusercontent.com/89567475/192808264-a83c3be4-70c4-4530-9dc0-b3f57367fdd1.png)

### 생성자 특징

-   리턴 타입이 없다.
-   클래스 이름과 함수 이름이 같다.
-   파라미터를 통해 초기화 가능하다.

### 생성자 예제

```java
class Pizza {
    int size;
    String type;

    public Pizza() {
        size = 12;
        type = "슈퍼슈프림";
    }

    public Pizza(int s, String t) {
        size = s;
        type = t;
    }
}

public class PizzaTest {

    public static void main(String[] args) {

        Pizza obj1 = new Pizza();
        System.out.println("(" + obj1.type + "," + obj1.size + ")");

        Pizza obj2 = new Pizza(24, "포테이토");
        System.out.println("(" + obj2.type + "," + obj2.size + ")");
    }
}
```

### 기본 생성자

```java
class A {
	int balance;
	public A { // 컴파일러에 의해 자동 삽입되는 '디폴트 연산자'
		//empty
	}

Public class HelloWorld {
	public static void main(String[] args) {
		A a = new A("")
```

-   기본 생성자(default constrcutor)는 매개 변수가 없는 생성자이다.
-   만약 개발자가 생성자를 하나도 정의하지 않으면 자바 컴파일러는 기본생성자를 자동으로 만든다.

### 생성자가 하나라도 있으면 디폴트 생성자는?

```java
class A {

	public A(String str) {
		System.out.pringln(str);
	}

Public class HelloWorld {
	public static void main(String[] args) {
		A a = new A("안녕하세요");

		A aa = new A();
```

-   개발자가 만들어 놓은 생성자가 있으면 컴파일러는 디폴트생성자를 생성하지 않는다.

## this 참조 변수

### this에 대한 이해

![스크린샷 2022-09-28 오후 11 32 41](https://user-images.githubusercontent.com/89567475/192808285-b5bf5aae-3b82-4beb-a26e-711a8ec12637.png)

-   this 는 현재 객체의 자신을 가리키는 참조 변수이다.
-   this 는 컴파일러에서 자동으로 생성한다.
-   흔히 생성자에서 매개변수 이름과 필드 이름이 동일한 경우에 혼동을 막기 위해서 사용한다.

```java
public class HelloWorld {

	public static void
```

### this() 함수

![스크린샷 2022-09-28 오후 11 34 47](https://user-images.githubusercontent.com/89567475/192808308-45d859aa-90a9-4d95-b820-64667b5ccaba.png)

-   this()는 다른 생성자를 의미한다.
-   this()는 다른 생성자를 호출할 때 쓰인다.
