# Lists

{% code overflow="wrap" lineNumbers="true" %}
```dart
void main() {
  var numbers = [2,3,4,5,6]; // var = List<int>
  numbers.add('Yongsun'); // Error: not allowed
  numbers.add(1);
}
```
{% endcode %}

* List\<E>를 명시해 주거나 var로 선언하여 사용

```dart
void main() {
  var giveMeFive = true;
  var numbers = [
    1,
    2,
    3,
    4,
    if (giveMeFive) 5, // List will have 5 if giveMeFive is true
  ];
  print(numbers);
}
// exact same code
void main() {
  var giveMeFive = true;
  var numbers = [1,2,3,4];
  if (giveMeFive) {
    numbers.add(5);
  }
  print(numbers);
}
```

* List 변수 내에서 if statement를 사용 가능하다.

## :gift: Advertisement

{% embed url="https://link.coupang.com/a/NDDuy" %}
"이 포스팅은 쿠팡 파트너스 활동의 일환으로, 이에 따른 일정액의 수수료를 제공받습니다."
{% endembed %}
