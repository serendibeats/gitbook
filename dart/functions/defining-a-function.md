# Defining a function

{% code overflow="wrap" lineNumbers="true" %}
```dart
String sayHello(String name) {
  return "Hello $name, nice to meet you!";
}
void main() {
  print (sayHello('Yongsun'));
}
// console: Hello Yongsun, nice to meet you!
```
{% endcode %}

* parameter 값을 $를 붙여서 바로 읽어서 사용 가능하다.

{% code overflow="wrap" lineNumbers="true" %}
```dart
String sayHello(String name) => "Hello $name, nice to meet you!";
void main() {
  print (sayHello('Yongsun'));
}
// console: Hello Yongsun, nice to meet you!
```
{% endcode %}

{% code title="example function" overflow="wrap" lineNumbers="true" %}
```dart
num plus(num a, num b) => a + b;
```
{% endcode %}

* 함수가 바로 return을 하면, 중괄호 { } 를 삭제하고, => 를 넣은 뒤 return value를 바로 적어서 사용할 수 있다.

## :gift: Advertisement

{% embed url="https://link.coupang.com/a/NDDuy" %}
"이 포스팅은 쿠팡 파트너스 활동의 일환으로, 이에 따른 일정액의 수수료를 제공받습니다."
{% endembed %}
