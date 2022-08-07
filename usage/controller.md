# Controller

The `mapController` property takes a `MapController()`, and whilst it is optional, it is strongly recommended for any map other than the most basic. It allows you to programmatically do actions with the map, such as moving it, rotating it and many other actions besides.

'flutter\_map' will handle disposing of this object for you, and that may not always be when you want, especially when having complex navigation in your app. If you get any errors about bad state or any errors with links to the controller, try the following method of initialising this property:

```dart
import 'package:flutter_map/flutter_map.dart';

// Inside the stateful widget

late final MapController mapController;

@override
void initState() {
    super.initState();
    mapController = MapController();
}

// Inside the build method of the stateful widget

FlutterMap(
    mapController: mapController,
),
```

There are other ways to call initialise and assign the controller, but this is the recommended way.

{% hint style="warning" %}
Don't be tempted to specify this property inside the `MapOptions()`. Always specify it at the top level of a `FlutterMap()` widget.
{% endhint %}