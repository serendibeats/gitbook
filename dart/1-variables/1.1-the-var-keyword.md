# The Var Keyword

{% code title="Var Keyword" overflow="wrap" lineNumbers="true" %}
```dart
void main() {
  var name = 'Yongsun';
}
```
{% endcode %}

* 변수의 Type을 구체화하지 않아도 된다
* 함수나 메소드 내부에 지역 변수를 선언할 때에 var를 사용한다.

{% code title="Type Error" overflow="wrap" lineNumbers="true" %}
```dart
void main() {
  var name = 'Yongsun';
  name = 1; // error
}
```
{% endcode %}

* 변수를 Update할 땐 원래 Type과 일치해야한다

{% code title="Explicitly specified type" overflow="wrap" lineNumbers="true" %}
```dart
void main() {
  String name = 'Yongsun';
}
```
{% endcode %}

* 명시적으로 변수의 타입을 지정 가능하다
* class에서 변수나 property를 선언할 때에는 타입을 지정해준다.

## :gift: Advertisement

{% embed url="https://link.coupang.com/a/NDDuy" %}
"이 포스팅은 쿠팡 파트너스 활동의 일환으로, 이에 따른 일정액의 수수료를 제공받습니다."
{% endembed %}
