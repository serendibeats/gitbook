# Named Parameters

{% code overflow="wrap" lineNumbers="true" %}
```dart
String sayHello(String name, int age, String country) {
  return "Hello $name, you are $age, and you come from $country";
}
void main() {
  print (sayHello('Yongsun', 8, 'Korea'));
}
```
{% endcode %}

* sayHello의 argument로 'Yongsun', 8, 'Korea'를 순서대로 주었다 (Positional argument).
* 함수의 사용자는 argument가 무엇을 의미하는지 알 수 없다.
* Not recommended as we can see in "clean code"

{% code overflow="wrap" lineNumbers="true" %}
```dart
String sayHello({String name = 'anonymous', int age = 99, String country = 'wacanda'}) {
  return "Hello $name, you are $age, and you come from $country";
}
void main() {
  print (sayHello(
    age: 8,
    name: 'Yongsun',
    country: 'Korea'
  ));
  
  print (sayHello);
}
// console output:
// Hello Yongsun, you are 8, and you come from Korea
// Hello anonymous, you are 99, and you come from wacanda
```
{% endcode %}

* sayHello 함수의 Parameter를 중괄호 { }로 바꿔주면 NameParameter로 사용가능하다.
* sayHello 함수의 argument를 key:value 형태로 바꿔서 사용한다.
* 함수를 사용하는 사용자가 parameter를 빼먹고 입력할 수 있기 때문에, Null Safety를 위해 NamedParameter의 default 값을 설정해주어 사용한다.

```dart
String sayHello({
  required String name,
  required int age,
  required String country,
}) {
  return "Hello $name, you are $age, and you come from $country";
}
void main() {
  print (sayHello(
    age: 8,
    name: 'Yongsun',
    country: 'Korea'
  ));
  
  print (sayHello());  // Error
}
```

* NamedParameter의 default 값을 지정하지 않고, 무조건 사용자로부터 값을 받고 싶다면 required keyword를 사용한다.
* required keyword가 적용된 NameParameter의 값을 주지 않는다면 Compile 시에 에러가 뜬다.

## :gift: Advertisement

{% embed url="https://link.coupang.com/a/NDDuy" %}
"이 포스팅은 쿠팡 파트너스 활동의 일환으로, 이에 따른 일정액의 수수료를 제공받습니다."
{% endembed %}
