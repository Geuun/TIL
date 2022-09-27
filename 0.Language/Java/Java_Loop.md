# Loop

# 반복문

-   실무에서는 for문을 가장 많이 쓰고, while문은 개발자의 성향에 따라 다르다.

### while문

```java
while(조건문){
	//조건문이 참(true)일때 실행되는 부분, 반복의 영역
}
```

-   while문은 조건문이 참/거짓이냐에 따라 한 번도 실행되지 않을 수 있다.
-   조건문이 `false`일 때까지 반복된다.

### do while문

```java
do{
	//반복의 영역
} while(조건문)
```

-   do while문은 while문과 다르게 조건에 상관없이 무조건 **한 번**은 실행된다.

### for 문

```java
for(int i = 0(초기식); i < 10(조건문); i++(증감문)){
	//반복의 영역
}
```

-   초기식 → 조건문`(if true)` → 반복의 영역 → 증감문 → 조건문 → 반복의 영역 → …

```java
// 구구단 출력 예제
Scanner sc = new Scanner(System.in);
int num = sc.nextInt();

for(int i=1; i<10; i++) {
	System.out.println(num + "x" + i + "=" + num*i);
}
```

### continue & break

continue

```java
// 1 ~ 100 사이에서 5의 배수이자 7의 배수, 그리고 그 개수를 찾는 예제
int cnt = 0;

for(int num=1; num<=100; num++) {
	if((num%5!=0) || (num%7!=0))
		continue;
	cnt++;
	System.out.println(num);
}
```

break

-   반복문을 빠져나가려면 `break`를 사용해서 빠져나갈 수 있다.

```java
// 5의 배수이자 7의 배수인 수를 찾는 예제
int num = 1;
boolean search = false;

while(num < 100){
	if((num % 5) == 0) && ((num % 7) == 0)){
		search = true;
		break;
	}
	num++;
}



if(search)
	System.out.println("찾는 정수: " + num);
```

### 반복문의 중첩 예제

```java
//구구단 출력하기

for(int i=2;i<10;i++) {
	for(int j=1;j<10;j++) {
		System.out.println(i + "x" + j + "=" + i*j);
	}
}
```

→ 내부 for문이 다시 j=1 부터 실행될 때, 새로운 메모리에 다시 j=1부터.

```java
//구구단 짝수만 출력하기

for(int i=2;i<10;i++) {
	if(i % 2 != 0)
		continue;
	for(int j=1;j<10;j++) {
		System.out.println(i + "x" + j + "=" + i*j);
	}
}
```

```java
for(int i=0;i<5;i++) {
	for(int j=0;j<5;j++) {
		System.out.print("*");
	}
	System.out.println();
}

>> *****
	 *****
	 *****
	 *****
	 *****

/* println은 print new line으로 개행!
	 print만 하면 다음 줄로 넘어가지 않음 */
```

```java
for(int i=0;i<5;i++) {
	for(int j=0;j<i+1;j++) {
		System.out.print("*");
	}
	System.out.println();
}

>> *
	 **
	 ***
	 ****
	 *****
```

```java
for(int i=0;i<5;i++) {
	for(int j=0;j<=5-i;j++) {
		System.out.print("*");
	}
	System.out.println();
}

>> *****
   ****
   ***
   **
   *
```

```java
for(int i=0;i<5;i++) {
	for(int j=0;j<5-i-1;j++) {
		System.out.print(" ");
	}
	for(int k=0;k<i+1;k++) {
		System.out.print("*");
	}
	System.out.println();
}

>>     *
      **
     ***
    ****
   *****

/* 두 번째 for문은 for(int j=5; j>i+1; j--) 이렇게도 가능. */
```
