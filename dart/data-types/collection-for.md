# Collection For

{% code overflow="wrap" lineNumbers="true" %}
```dart
void main() {
  var oldFriends = ['nico', 'lynn'];
  var newFriends = [
    'lewis',
    'ralph',
    'darren',
    for (var friend in oldFriends) "❤️ $friend"
  ];
  print(newFriends);
}
// console: [lewis, ralph, darren, ❤️ nico, ❤️ lynn]
```
{% endcode %}

{% code title="위와 같은 코드" overflow="wrap" lineNumbers="true" %}
```dart
void main() {
  var oldFriends = ['nico', 'lynn'];
  var newFriends = [
    'lewis',
    'ralph',
    'darren',
  ];
  for (var friend in oldFriends) {
    newFriends.add('❤️ $friend');
  }
  print(newFriends);
}
```
{% endcode %}

* collection if 와 마찬가지로 List 안에서 For loop을 사용할 수 있다.
* UI Interface를 만들 때 많이 활용 된다.
