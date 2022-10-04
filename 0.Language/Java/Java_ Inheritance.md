# 상속

### 상속에 대한 이해

```java
class Car{
	int speed; //속도
	public void setSpeed(int speed) {// 속도 변경 메소드
		this.speed = speed;
	}
}

public class ElectricCar extends Car
{
	int battery;

	public void charge(int amount) {// 충전 메소드
		battery += amount;
	}
}
```

```java
public class ElectricCarTest {
	public static void main(String[] args) {

		ElectricCar obj = new ElectricCar();

		obj.speed = 10;//// 부모 멤버 사용
		obj.setSpeed(60);// 부모 멤버 사용
		obj.charge(10);//// 추가된 메소드 사용
	}
}
```

### 상속을 사용하는 이유

-   상속을 사용하면 `중복되는 코드를 줄일 수 있다.`
-   상속받아서 이미 존재하는 `클래스의 필드와 메소드를 재사용할 수 있다.`

### 생성자 호출 순서

-   직계 부모 클래스를 찾아간다.
-   부모에게도 상속받은 클래스가 있다면 최상위 부모 클래스까지 찾아간다.
-   이후 상속관계를 따라 내려오면서 호출된다.
-   따라서 부모 클래스의 생성자 → 자식 클래스의 생성자 순서로 호출하게 된다.

### 왜 자식 객체 생성시 부모생성자 까지 호출 되는가?

-   자식 클래스 객체 안에는 부모 클래스에서 상속된 부분이 들어 있다.
-   따라서 자식 클래스 안의 부모 클래스 부분을 초기화하기 위해서 부모 클래스의 생성자도 호출되는 것이다.

### 명시적인 생성자 호출 `super()`

-   `super()`를 호출하면 부모 클래스 생성자 호출

묵시적인 생성자 호출 `super()`

-   컴파일러는 부모 클래스의 기본 생성자가 자동 호출

-   부모 클래스 생성자 선택

![스크린샷 2022-09-26 오전 10 35 58](https://user-images.githubusercontent.com/89567475/193718227-96b08e17-7ef6-4b23-b09b-58a20a81e374.png)

    인수 형태에 다라 적절한 생성자가 선택된다.

-   오류가 발생하는 경우

![스크린샷 2022-09-26 오전 10 37 31](https://user-images.githubusercontent.com/89567475/193718235-19abc8d8-64e2-4df9-b301-d13dac5d11a9.png)

    부모 클래스에 기본 생성자가 없기 때문에 호출할 생성자가 없어서 생기는 오류.

`protected` : 상속시 다른 패키지에서도 접근가능!

Q. import는 상속과 같은 역할을 할 수 없나요?

-   A. import와 상속의 사용 목적이 다릅니다.
    1. import문은 컴파일러에게 소스파일에 사용된 클래스의 패키지에 대한 정보를 제공하기 위해 명시하는 것
    2. 상속은 기존의 클래스에 새로운 변수와 메서드를 추가하여 새로운 클래스를 만드는 것이기에 유지보수에 용이하게 하기 위함.
       import문으로 다른 패키지의 클래스를 명시하여 사용할 순 있습니다. 그렇게 되면 코드의 유연성과 가독성 그리고 유지보수가 많이 떨어집니다.
