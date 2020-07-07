### Disable Night Mode in iOS Swift

> Add User Interface Style to Light in Info.plist

> In AppDelegate.swift, add this code

```sh
        // DISABLE DARK MODE
        if #available(iOS 13.0, *) {
            UIWindow.appearance().overrideUserInterfaceStyle = .light
        }
```
