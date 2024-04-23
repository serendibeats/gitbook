# Sets

{% code overflow="wrap" lineNumbers="true" %}
```dart
void main() {
  var numbers = {1,2,3,4}; // Set<int>
  numbers.add(1);
  numbers.add(1);
  numbers.add(1);
  numbers.add(1);
  print (numbers);
}
// console: {1, 2, 3, 4}
```
{% endcode %}

* Set은 중괄호 { } 로 선언하여 사용한다. (:information\_source: List는 대괄호 \[ ] 이다)
* numbers의 Type은 Set\<int> 이다.
* 같은 element는 하나로 친다.
