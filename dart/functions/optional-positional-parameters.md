# Optional Positional Parameters

{% code overflow="wrap" lineNumbers="true" %}
```dart
String sayHello(String name, int age, [String? country = 'cuba']) {
  return "Hello $name, you are $age, and you come from $country";
}
void main() {
  print (sayHello('Yongsun', 8));
}
// console: Hello Yongsun, you are 8, and you come from cuba
```
{% endcode %}

* positional argument중에 특정 argument(country)들을 optional로 하려고 한다.
* optional 로 하려고 하는 argument를 대괄호 \[ ]로 묶어준 뒤, country를 ? 를 사용하여 [1.3-nullable-variables.md](../1-variables/1.3-nullable-variables.md "mention")로 바꿔준다.&#x20;
* 그리고 Nullable variable의 default 값을 지정해서 사용한다.

## :gift: Advertisement

{% embed url="https://link.coupang.com/a/NDDuy" %}
"이 포스팅은 쿠팡 파트너스 활동의 일환으로, 이에 따른 일정액의 수수료를 제공받습니다."
{% endembed %}
