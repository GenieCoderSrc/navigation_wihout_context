# navigation_wihout_context

A lightweight Flutter package that simplifies navigation without requiring `BuildContext`. Easily push, pop, replace, or reset navigation stacks using a global navigator key.

## Features

- Navigate between routes without needing context.
- Push named routes with or without arguments.
- Replace routes or remove all previous ones.
- Useful for service-based or ViewModel-driven architecture.

## Getting Started

Add the package to your `pubspec.yaml`:

```yaml
dependencies:
  navigation_wihout_context: ^0.0.1
```

## Usage

1. Set up the `navigatorKey` in your `MaterialApp`:

```dart
import 'package:flutter/material.dart';
import 'package:navigation_wihout_context/navigation_wihout_context.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      navigatorKey: AppRouter.navigatorKey,
      routes: {
        '/': (context) => HomePage(),
        '/second': (context) => SecondPage(),
      },
    );
  }
}
```

2. Navigate without `BuildContext`:

```dart
AppRouter.pushNameRoute('/second', arguments: {'message': 'Hello'});
AppRouter.popRoute();
AppRouter.pushReplacementRoute('/second');
AppRouter.pushNamedAndRemoveUntil('/second');
AppRouter.popAndPushNamed('/second');
```

## API

- `AppRouter.navigatorKey`: Global navigator key for use in `MaterialApp`.
- `pushNameRoute(String route, {dynamic arguments})`
- `popRoute()`
- `pushReplacementRoute(String route, {Object? arguments})`
- `pushNamedAndRemoveUntil(String route, {Object? arguments})`
- `popAndPushNamed(String route, {Object? arguments})`

## License

MIT License

## Contributions

Contributions, issues and feature requests are welcome!

Feel free to check [issues page](https://github.com/GenieCoderSrc/navigation_wihout_context).

