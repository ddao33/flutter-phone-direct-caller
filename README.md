# flutter_phone_direct_caller

flutter_phone_direct_caller with PR merged to fix issues with iOS and Android. Original repo is not maintained and does not work with latest Flutter.

Original repo: https://github.com/yanisalfian/flutter-phone-direct-caller

## Usage

Add dependency to pubspec.yaml file

```
  flutter_phone_direct_caller:
    git:
      url: git@github.com:ddao33/flutter-phone-direct-caller.git
      ref: master
```

### Android
No need any additional configuration.

### iOS
Add this to your ```info.plist``` under ```dict``` 
```
<key>LSApplicationQueriesSchemes</key>
<array>
  <string>tel</string>
</array>
```

## Example

```dart
import 'package:flutter/material.dart';
import 'package:flutter_phone_direct_caller/flutter_phone_direct_caller.dart';

void main() {
  runApp(Scaffold(
    body: Center(
      child: RaisedButton(
        onPressed: _callNumber,
        child: Text('Call Number'),
      ),
    ),
  ));
}

_callNumber() async{
  const number = '08592119XXXX'; //set the number here
  bool res = await FlutterPhoneDirectCaller.callNumber(number);
}
```

