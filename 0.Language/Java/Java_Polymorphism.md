# 다형성 (polymorphism)

### 다형성의 이해

다형성이란?

-   객체들의 타입이 다르면 똑같은 메세지가 전달되더라도 서로 다른 동작을 하는 것이다.

객체간의 Casting

![스크린샷 2022-09-26 오후 1 47 24](https://user-images.githubusercontent.com/89567475/194761894-246c8fed-6579-4bbd-8bfb-0256d7a6ee95.png)

-   `부모 = 자식`
-   오버라이딩은 자식꺼

```java
Shape s1 = new Shape();
Shape s2 = new Circle();

==> 가능할까?
```

<img width="199" alt="스크린샷 2022-09-26 오후 3 12 12" src="https://user-images.githubusercontent.com/89567475/194761926-47211058-e6b9-439c-9633-ca55fa0923a1.png">

<img width="468" alt="스크린샷 2022-09-26 오후 3 12 22" src="https://user-images.githubusercontent.com/89567475/194761930-09a5b500-0565-4bde-9720-d152c27143cb.png">

![스크린샷 2022-09-27 오전 9 45 04](https://user-images.githubusercontent.com/89567475/194761933-901a5b3a-3491-4f6d-aa3f-ae56e3b70254.png)

### 업케스팅

`Shape shape = new Circle()`

-   gkdnl rorcpfmf tkddnl zmffotmgud qustndp eodlq
-   부모 클래스 변수로 자식 클래스 객체를 참조할 수 있다.
-   이것을 업캐스팅(Upcasting, 상형 형변환) 이라고 한다.

### 다운캐스팅

```java
Shape cirleShape = new Circle(10);

Circle circle = (Circle) circleShape; // 미리 자식으로 메모리에 올라가 있으면 가능하다.

System.out.println(circle.getArea());
```

-   다형성 적용으로 잃어버린 특성을 복구시키기 위해 원래 상태로 되돌리는 것.
-   다운캐스팅은 업캐스팅을 해서 메모리에 올린 뒤 가능하다.

### 업캐스팅 다운캐스팅 예제

```java
class Parent {
    void print() {
        System.out.println("Parent 메소드 호출");
    }
}

class Child extends Parent {
    @Override
    void print() {
        System.out.println("Child 메소드 호출");
    }
}

public class Casting {

    public static void main(String[] args) {

        Parent p = new Child();     // 업캐스팅: 자식 객체를 부모 객체로 형변환
        p.print();                  // 동적 메소드 호출, 자식의 print() 호출

        // Child c = new Parent();  // 컴파일 오류

        Child c = (Child)p;         // 다운캐스팅: 부모 객체를 자식 객체로 형변환
        c.print();                  // 메소드 오버라이딩, 자식 객체의 print() 호출
    }
}
```

### 다형성의 활용

```java
public class ShapeTest {

	public static void print(Shape s) {
		System.out.println("x=" + s.x + " y=" + s.y);
	}

	public static
}
```

### instanceof 연산자

-   객체의 실제 타입을 알고싶을 때 사용하는 연산자
-   Instanceof 연산자는 기본적으로 `true`, `false`를 반환한다.

```java
// 활용 예제

public static void print(Shape shape) {

	if( shape instanceof Rectangle) {  // 캐스팅 가능 여부를 묻는다.
			System.out.println("실제 타입은 Rectangle 입니다.");
	} else if( shape instanceof Circle) {
			System.out.println("실제 타입은 Circle 입니다.");
	} else {
			System.out.println("알 수 없는 타입입니다.");
	}
}
```

### instanceof 참고사항

```java
// 클래스(참조형) 타입은 가능!
if("geun" instanceof String) { } // String 타입이므로 true

// 컴파일 오류! primitive type은 instanceof 적용 불가능!.
if(3 instanceof int) { }
```
