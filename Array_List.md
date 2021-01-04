# 자신이 사용하고 있는 프로그래밍 언어가 제공하는 배열과 리스트 자료 구조에 대해 학습하세요.

## 언어: Java

### 배열
> 자료형의 집합


```java
// int 타입 배열 선언
int[] i_array;
int i_aray[];

// 배열 생성 후 초기화하면 배열의 주소가 할당
int i_array = new int[3]; // 초기값 0
String s_arrray = new String [8]; // 초기값 ""

// 배열 선언을 먼저 하고 나중에 초기화도 가능
int [] i_array;
i_array = new array[8];

// 배열에 특정값 대입하며 선언
int[] i_array = {1, 2, 3};

// 배열을 모두 같은 값으로 초기화
Arrays.fill(i_array, 1); // 1로 초기화

for(int i :
	i_array) {
	i_ array[i] = 1;
}

// 다차원 배열
String[][] friends = new String[2][3];

int[][] grades = {
	{95, 75, 100},
	{100, 85, 90}
	}
```
__객체 배열 사용법__
```java
Apple[] apple = new Apple[3];	// 각 배열에는 null 값만 존재

// 배열 안의 클래스 초기화 필요
for(int i:
	apple) {
	apple[i] = new Apple();
}

```

__Arrays 클래스__
> java.util.Arrays에 포함
>> 모든 메소드는 클래스 메소드(static method)이므로, 객체를 생성하지 않고 바로 사용 가능

__대표적인 Arrays 메소드__
|메소드|설명|
|:--:|:--:|
|static <T> List<T> asList(T... a)|전달받은 배열을 고정 크기의 리스트(list)로 변환하여 반환함.|
|static int binarySearch(Object[] a, Object key)|전달받은 배열에서 특정 객체를 이진 검색 알고리즘을 사용하여 검색한 후, 그 위치를 반환함.|
|static <T> T[] copyOf(T[] original, int newLength)|전달받은 배열을 특정 길이의 새로운 배열로 복사하여 반환함.|
|static <T> T[] copyOfRange(T[] original, int from, int to)|전달받은 배열의 특정 범위에 해당하는 요소만을 새로운 배열로 복사하여 반환함.|
|static boolean equals(Object[] a, Object[] a2)|전달받은 두 배열이 같은지를 확인함.|
|static void fill(Object[] a, Object val)|전달받은 배열의 모든 요소를 특정 값으로 초기화함.|
|static void sort(Object[] a)|전달받은 배열의 모든 요소를 오름차순으로 정렬함.|

### 리스트
> java.util.List에 포함
>> 인터페이스 클래스이며, java.util.Collection 인터페이스를 구현한 것

```java
// List를 사용하기 위해서는 아래 클래스들 중 하나로 인스턴스화
import java.util.ArrayList;
import java.util.LinkedList;
import java.util.List;
import java.util.Stack;
import java.util.Vector;

List listA = new ArrayList();
List listB = new LinkedList();
List listC = new Stack();
List listD = new Vector();
```

__값을 추가하기__
```java
List list = new ArrayList();

list.add("C");
list.add("Java");
list.add(new String("Python"));
// 원하는 위치에 삽입
list.add(1, "Swift");
```

__값을 꺼내기__
```java
String data = list.get(0).toString();

// Iterator를 통한 전체 조회
Iterator iterator = list.iterator();
while (iterator.hasNext()) {
	String element = (String) iterator.next();
}

// for-loop를 통한 전체 조회
for(Object object:
	list) {
	String element = (String) object;
}
```

__값을 삭제하기__
```java
// 인덱스를 통해 검색 후 삭제 (삭제된 값 리턴)
list.remove(2);
// 오브젝트를 통해 삭제 (삭제여부 true OR false 리턴)
list.remove("Swift");
```

__값이 있는 지 확인__
```java
// boolean return
list.contains("Java");
```

__특정 위치에 값을 넣기__
```java
String index = list.indexOf("Python");
// Python 앞에 추가
list.add(index, "Kotlin");
```