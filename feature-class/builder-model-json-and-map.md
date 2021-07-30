# Builder Model \(json & map\)

### Setting

in `./build.yaml`

### How to use

1. run command

   ```text
   $ flutter packages pub run build_runner watch --delete-conflicting-outputs
   ```

2. open [json2dart-model ](https://imagine10255.github.io/json2dart-model/)website
3.  copy your json string

```dart
import 'package:json_annotation/json_annotation.dart'; // <~ this
import 'package:copy_with_extension/copy_with_extension.dart'; // <~ this

part 'state.g.dart'; // <~ this

@JsonSerializable() // <~ this
@CopyWith() // <~ add this
class System {
  System({
    this.isFetching = false,
  });

  bool? isFetching;
 
  /// JsonSerializable Build
  factory System.fromJson(Map<String, dynamic> json) => _$SystemFromJson(json); // <~ add this
  Map<String, dynamic> toJson() => _$SystemToJson(this); // <~ add this
}
```

{% hint style="info" %}
if you need use one, run commend

```bash
$ flutter packages pub run build_runner build --delete-conflicting-outputs
```
{% endhint %}
