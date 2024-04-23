# Maps

{% code overflow="wrap" lineNumbers="true" %}
```dart
void main() {
  var player = {
    'name': 'Yongsun',
    'xp': 19.99,
    'superpower': false,
  };
  print (player);
}
```
{% endcode %}

* player의 Type은 Map\<String, Object>이다.
* key:value data structure이며, value의 Type이 Object이므로 어떤 값이 와도 된다.

{% code overflow="wrap" lineNumbers="true" %}
```dart
void main() {
  Map<int, bool> player = {
    1: true,
    2: false,
    3: true,
  };
  print (player);
}
```
{% endcode %}

* 위와 같이 key:value의 type을 지정 가능하다.
