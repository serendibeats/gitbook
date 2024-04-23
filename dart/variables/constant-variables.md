# Constant Variables

{% code title="" overflow="wrap" lineNumbers="true" %}
```dart
void main() {
  const KEY1 = '1234';
  const KEY2 = fetchKey(); // Error
}
```
{% endcode %}

* Javascript나 Typescript에서의 const는 final과 비슷하다.
* :star:Dart에서 const는 compile-time constant를 만들어준다.
* KEY2의 경우 Compile 시점에 어떤 값인지 알 수 없기 때문에 Error가 난다.
