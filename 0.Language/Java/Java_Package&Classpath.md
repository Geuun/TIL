# 패키지 & 클래스 path

### 패키지란?

-   비슷한 성격의 자바 클래스들을 모아놓은 것으로, 내장 패키지와 사용자 정의 패키지로 분류할 수 있다.
-   패키지의 이름은 모두 소문자로 구성된다
-   인터넷 도메인 이름의 역순으로 이름을 구성하고, 이름의 끝에 클래스를 정의한 팀 또는 프로젝트의 이름을 추가한다.
    ex. [www.wxfx.com](http://www.wxfx.com/) -> com.wxfx.smart

### 패키지가 필요한 이유

1. 같은 위치에 똑같은 이름의 클래스 파일(.java)을 둘 수 없다.

-   패키지 com.wxfx.smart는 com이라는 폴더에 wxfx라는 폴더에 있는 smart라는 폴더에 클래스를 위치시켜 동일한 이름의 클래스가 다른 위치에 놓이도록 한다

1. 다른 위치에 있는 똑같은 이름의 클래스를 실행하면 동일한 이름의 인스턴스가 생성되어 충돌이 일어난다.

-   다른 위치에 있는 똑같은 이름의 클래스를 가져오고 싶은 경우 패키지 이름까지 가져온다

```java
// 클래스 이름은 Circle로 동일함

com.wxfx.smart.Circle circle1 = new com.wxfx.smart.Circle();
com.fxmx.simple.Circle circle1 = new com.fxmx.simple.Circle();
```

### 터미널을 이용하여 컴파일, JVM 동작 시키기

1. 소스코드 컴파일

-   javac <클래스 이름>.java
    → 클래스 파일 <클래스 이름>.class 형성

ex. javac JavaProject.java

### 클래스를 JVM에 올리기

1. java <클래스 이름>
   → 이때 <클래스 이름>.class가 아니라 <클래스 이름>만 입력

ex. java JavaProject

### JVM이 클래스를 찾는 3가지 방법

1. 주어진 것이 없으면 현재 디렉터리부터 찾는다
2. 환경변수 classpath에 해당 클래스가 위치한 경로를 설정해준다.

### (터미널의 경로 자체 변경)

-   경로를 설정해주면 terminal이 해당 경로에서 실행된다.
-   set classpath = <클래스가 위치한 경로>

set classpath = C:\Users\doit\Documents\workspace-sts 3.9.11.RELEASE\java_jvm\src

### 가상 머신을 실행할 때 -classpath라는 옵션을 이용한다. (JVM을 실행할 때에만 변경)

-   가장 권장되는 방법이다.
-   실행 후에는 원래의 디렉토리에서 터미널이 실행된다.
-   java -classpath <경로> java <클래스 이름>

ex. java -classpath C:\Users\doit\Documents\workspace-sts-3.9.11.RELEASE\java_jvm\src java JavaProject

### 💡 **classpath란 무엇인가?**

터미널이 실행되는 경로를 받아주는 환경변수, set classpath를 하면 터미널이 실행되는 경로를 설정할 수 있다.
