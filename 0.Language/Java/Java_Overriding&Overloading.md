# 오버라이딩 & 오버로딩

-   면접에서 많이 물어보는 질문 중 하나이다.

![스크린샷 2022-09-26 오후 1 09 15](https://user-images.githubusercontent.com/89567475/193718934-644cd568-0df0-495c-a285-d9a1662938e8.png)

### 매소드 `Override`(오버라이딩)이란?

-   자식 클래스가 부모 클래스의 메소드를 자신의 필요에 맞추어 재정의
-   함수 바디만 달리하여야한다.
-   예제

    ```java
    class Shape{
    	public void draw() {
    		System.out.println("도형을 그립니다.");
    	}
    }

    class Rectangle extends Shape{
    	@Override
    	public void draw() {
    		System.out.println("사각형을 그립니다.");
    	}
    }

    public class Test2 {

    	public static void main(String[] args) {
    		Shape shape = new Shape();
    		shape.draw();

    		Rectangle rectangle = new Rectangle();
    		rectangle.draw();

    	}
    }

    >> 도형을 그립니다.
       사각형을 그립니다.
    ```

### 매소드 오버라이딩

![스크린샷 2022-09-27 오전 10 25 33](https://user-images.githubusercontent.com/89567475/193718942-8d148912-6c3a-4baf-b494-d9148dc32230.png)

### 오버라이딩된 메소드 호출

![스크린샷 2022-09-27 오전 10 25 57](https://user-images.githubusercontent.com/89567475/193719030-a3527bcb-a160-420a-8f21-7eb1cb554b73.png)

-   오버라이딩 된 메소드를 인스턴스 외부에서 호출하는 방법은 없다.
-   인스턴스 내부에서는 `super` 키워드를 이용해서 호출 가능하다.

### 매소드 `Overload`(오버로딩)이란?

-   상속관계가 아니어도 된다.

```java
public double getArea(double radius){}
public double getArea(int radius){}
public double getArea(int radius, int n){}
```

-   같은 함수 이름으로 파라미터의 데이터타입 또는 갯수를 달리할 수 있다.
