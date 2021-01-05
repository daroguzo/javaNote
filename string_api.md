### 자신이 사용하는 프로그래밍 언어가 제공하는 문자열 관련 API를 학습하세요.

## 언어: Java

__String 생성자__
> 자바의 문자열은 java.lang 패키지의 String 클래스의 인스턴스로 관리
>> String클래스의 다양한 생성자를 이용해서 직접 String 객체 생성 가능

```java
// 배열 전체를 Stirng 객체로 생성
String str = new String(byte[] bytes);

// 지정한 문자셋으로 디코딩
String str = new String(byte[] bytes, String charsetName);

// 배열의 offset 인덱스 위치부터 length 만큼 String 객체로 생성
Strign str = new String(byte[] bytes, int offset, int length);

// 지정한 문자셋으로 디코딩
String str = new String(byte[] bytes, int offset, int length, String charsetName);

// 바이트 배열을 문자열로 변환
byte[] bytes = {74, 97, 118, 97};

String str1 = new String(bytes);
System.out.println(str1);	// Java

String str2 = new String(bytes, 2, 2);
System.out.println(str2);	// va
```
__String 클래스에서 자주 사용되는 메소드__
|리턴 타입|메소드 명(매개 변수)|설명|
|:--:|:--:|:--:|
|char|charAt(int index)|특정 위치의 문자 리턴|
|boolean|equals(Object object)|두 문자열 비교|
|byte[]|getBytes()|byte[]로 리턴|
|byte[]|getBytes(Charset charset)|주어진 문자셋으로 인코딩한 byte[]로 리턴|
|int|indexOf(String str)|문자열 내에서 주어진 문자열의 위치를 리턴|
|int|length()|총 문자의 수를 리턴|
|String|replace(CharSequence target, CharSequence replacement)|target 부분을 replacement로 대치한 후 새로운 문자열을 리턴|
|String|substring(int beginIndex)|beginIndex 위치에서 끝까지 잘라낸 새로운 문자열 리턴|
|String|substring(int beginIndex, int endIndex)|beginIndex 위치에서 endIndex 전까지 잘라낸 새로운 문자열을 리턴|
|String|toLowerCase()|알파벳 소문자로 변환한 새로운 문자열 리턴|
|String|toUpperCase()|알파벳 대문자로 변환한 새로운 문자열 리턴|
|String|trim()|앞뒤 공백을 제거한 새로운 문자열 리턴|
|String|valueOf(int i) valueOf(double d)|기본 타입값을 문자열로 리턴|

__StringBuilder와 StringBuffer__
> java.lang 소속
>> String 클래스가 문자열을 생성자로 넣어 인스턴스를 한 번 생성하고 나면 인스턴스가 가진 문자열 값을 변경하지 못하는 단점을 보완한 클래스(여유가 있는 공간으로 생성)
>>> 두 가지 모두 쓰임과 메소드가 같지만, StringBuffer는 여러 곳에서 동시에 같은 문자열 인스턴스에 접근할 때 중복 점유를 막을 수 있는 장치 보유(동기화 처리, 무거움)

__String 클래스와 동일 메소드__
+ charAt()
+ indexOf() / lastIndexOf()
+ length()
+ replace()
+ substring()
+ toString()

__추가적인 메소드__
append(String str)
> 문자열 추가

capacity()
> String 클래스와 다르게 여유있게 잡아둔 char[]배열 사이즈 정보 반환

delete(int beginIndex, int EndIndex)
> 매개변수로 전달받은 인덱스 사이의 문자열 제거

deleteCharAt(int deleteIndex)
> 특정 인덱스의 한 문자만 삭제

insert(int insertIndex, String str)
> 특정 위치에 문자열 삽입

reverse()
> 문자열을 거꾸로 뒤집기

setCharAt(int index, char ch)
> 특정 위치의 문자 변경

setLength(int len)
> 문자열 길이 조정(현재 문자열보다 길게 조정하면 공백, 짧게 조정하면 나머지 삭제)

trimToSize()
> 문자열이 저장된 char[] 배열 사이즈를 현재 문자열 길이와 동일하게 조정 

```java
StringBuilder sb = new StringBuilder("Hello");

sb.append(" Java"); // Hello Java

sb.capacity();	// length는 9이지만 더 큰 수가 나옴

sb.delete(6, 9);	// Helloa

sb.delete(6);	// Hello

sb.insert(6, "Java");	// Hello Java

sb.reverse();	// avaJ olleH

sb.setCharAt(3, 'j');	// avaj olleH

sb.setLength(3);	// avaj

sb.trimToSize();
sb.capacity();	// 3
```