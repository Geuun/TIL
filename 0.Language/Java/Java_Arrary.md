# Arrary

### 배열이 필요한 이유

-   여러개의 데이터를 효과적으로 처리하고 관리하기 위해서

![Array](https://user-images.githubusercontent.com/89567475/192521831-4b190c10-be1b-4406-aa15-6764122dc364.png)

### 배열의 선언 방법

![Array](https://user-images.githubusercontent.com/89567475/192522316-3e71d475-f5c9-4420-b96c-e2a2fae21bdf.png)

```java
// int공간 10개를 선언
int[] arr = new int[10];

// 선언 시 바로 초기화
int[] arr = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
```

### 반복문과 배열

-   arr[index]를 활용하여 값을 불러오고 넣을 수 있다.

```java
public class charater {

	public static void main(String[] args) {

		int[] arr = new int[1000];
		int result = 0;

		// index = 0이고, result = 1부터 넣어야 한다.
		for (int i = 0; i < 1000; i++) {
			arr[i] = i+1;
		}

		for (int i = 0; i < 1000; i++) {
			result += arr[i];
		}
		System.out.println(result);
	}
}
```

### 배열 - for each loop

```java
int[] arr = new int[10];

for (int num : arr) {
    System.out.print(num);
}
```

### 배열 사용시 메모리 할당 방식

-   배열은 스택에 4byte로 올라가고 스택에는 heap공간에 메모리 주소가 저장된다.
-   데이터 타입만큼의 크기로 heap메모리에 나열되있다.
-   배열 자체에는 첫 주소값이 들어있다.
