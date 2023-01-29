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

## :gift: Advertisement

{% embed url="https://link.coupang.com/a/NDDuy" %}
"이 포스팅은 쿠팡 파트너스 활동의 일환으로, 이에 따른 일정액의 수수료를 제공받습니다."
{% endembed %}
