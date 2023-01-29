# Late Variables

{% code title="late variables" overflow="wrap" lineNumbers="true" %}
```dart
void main() {
  late final String name;
  // do something, go to api
  name = 'Yongsun'; // This works.
  name = 'Hello';  // Error
}
```
{% endcode %}

* late는 초기에 데이터 없이 변수를 선언할 수 있게 해준다.
* final과 함께 사용해도 데이터를 나중에 할당 해 줄 수 있다. 하지만 할당 이후에 변경은 불가능하다.
* Flutter에서 data fetching할 때 유용하다.

## :gift: Advertisement

{% embed url="https://link.coupang.com/a/NDDuy" %}
"이 포스팅은 쿠팡 파트너스 활동의 일환으로, 이에 따른 일정액의 수수료를 제공받습니다."
{% endembed %}
