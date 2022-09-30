## 접근제한자 (Access Modifier)

![스크린샷 2022-09-30 오후 4 56 04](https://user-images.githubusercontent.com/89567475/193263502-9a1780bc-ae5d-4582-8f2e-88528823ac8f.png)

-   클래스 : public, default (아무것도 없는 것)
-   메소드, 변수 : public, protected, default, private

### 클래스의 접근 제한자

-   `public` : 어디서든 인스턴스 접근 및 생성이 가능하다.
-   `default`: 동일 패키지와 묶인 클래스 내에서만 인스턴스 접근 및 생성을 허용한다.
    → 다른 패키지에서는 인스턴스 접근 및 생성이 불가능하다.
        ```java
        import car.Hcar;
        import car.Scar; //컴파일 에러

        public class JvmTest {

        	public static void main(String[] args) {
        		Hcar hcar = new Hcar();
        		Scar scar = new Scar(); //컴파일 에러
        	}
        }
        ```

### 다른 접근 제한자(변수, 메소드)

-   private: 자기 클래스 내에서만 접근이 가능하다. 외부(다른 클래스, 다른 패키지)에서는 접근이 불가능 하다.
-   default: 같은 패키지 내의 클래스에서는 접근이 가능하다. 즉, **다른 패키지에서는 접근이 불가능!!**
-   protected: 같은 패키지 내의 클래스에서 접근이 가능하고, 추가적으로 다른 패키지라도 해당 클래스를 상속받는 자식 클래스에서는 접근이 가능하다.
-   public: 어디서든 다 접근이 가능하다.

<img width="603" alt="Untitled" src="https://user-images.githubusercontent.com/89567475/193263519-6fd2eb40-9e82-478f-b539-8eac22291816.png">

### 주의사항!

-   하나의 자바 파일에서는 반드시 한개의 public class만 허용한다.
-   생성자도 메소드이다! 따라서 생성자 또한 접근 제한자를 잘 설정해주어야 올바른 객체 생성이 가능하다.
    클래스는 public으로 설정했는데 생성자는 default로 한 경우, 참조형 변수 선언은 가능하지만 객체가 생성되지는 않는다.
