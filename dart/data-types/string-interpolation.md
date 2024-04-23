# String interpolation

{% code overflow="wrap" lineNumbers="true" %}
```dart
void main() {
  var name = 'Yongsun';
  var age = 10;
  var greeting = "Hello everyone, My name is $name. I'm ${age + 2}";
  print(greeting);
}
// console: Hello everyone, My name is Yongsun. I'm 12
```
{% endcode %}

* String interpolation은 text에 변수를 추가하는 방법이다.&#x20;
* Flutter에서 많이 쓰인다.
* String 변수 안에서 $변수명 을 사용하면 된다.
* 변수의 연산이 필요하다면 $뒤에 { }를 사용햔다.
