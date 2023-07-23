# Wait Keyboard Height for Flutter

`wait_keyboard_height` is a Flutter plugin for iOS and Android that provides the keyboard size before the keyboard animation occurs for showing or hiding it. This helps eliminate lag when positioning widgets around the keyboard, such as placing a TextField above the keyboard.

`wait_keyboard_height` is a downgraded plugin version flutter sdk and it depends on package ''keyboard_height_plugin: https://pub.dev/packages/keyboard_height_plugin'

## Installation

To install `wait_keyboard_height`, add it to your `pubspec.yaml` file under the `dependencies` section:

```yaml
dependencies:
  wait_keyboard_height: ^0.0.1
```

## Usage

To use the `wait_keyboard_height`, first import it in your Dart file:

```dart
import 'package:wait_keyboard_height/wait_keyboard_height.dart';
```

Next, create a stateful widget and declare a variable to store the keyboard height and create an instance of the `KeyboardHeightPlugin`:

```dart
class _HomePageState extends State<HomePage>; {
  double _keyboardHeight = 0;
  final WaitKeyboardHeight _waitKeyboardHeight_ = WaitKeyboardHeight();
  // ... rest of code ...
}
```

Then, initialize the `WaitKeyboardHeight` in your `initState` method and listen for changes in the keyboard height:

```dart
@override
void initState() {
  super.initState();
  _waitKeyboardHeight_.onKeyboardHeightChanged((double height) {
    setState(() {
      _keyboardHeight = height;
    });
  });
}
```

Use the `_keyboardHeight` variable to position your widgets around the keyboard. 

## Example

For a complete example on how to use the `wait_keyboard_height`, please refer to the [`example`](example) directory in the repository.

## Contributing

If you encounter any issues or have suggestions for improvements, feel free to open an issue or submit a pull request on the project's GitHub repository.

## License

This plugin is licensed under the [BSD 3-Clause License](LICENSE).
