# 선택문 If문

### if 문

```java
if (true or false) {
	조건이 true 시 실행되는 영역
}
```

-   if문에 속한 문장이 하나일 경우에는 중괄호를 생략해서 한줄로 표현 가능하다.

### else if문

```java
if(true or false) {
	조건 true 시 실행되는 영역
} else if (true or false){
	else if 의 조건이 true시 실행되는 영역
} else {
	위 조건들이 다 만족하지 않는경우 실행되는 영역
}
```

-   if문과 마찬가지로 if절 또는 else절에 속한 문장이 하나일 경우 중괄호 생략가능

### switch 문

```java
public class SwitchTest {

    public static void main(String[] args) {

        int n = 3;

        switch(n) {
            case 1:
                System.out.println("Simple Java");
            case 2:
                System.out.println("Funny Java");
            case 3:
                System.out.println("Fantastic Java");
            default:
                System.out.println("The best programming language");
        }

        System.out.println("Do you like Java?");
    }
}
```

```java
public class SwitchTest {

    public static void main(String[] args) {

        int n = 3;

        switch(n) {
            case 1:
            case 2:
            case 3:
                System.out.println("case 1, 2, 3");
                break;

            default:
                System.out.println("default");
        }
    }
}
```
