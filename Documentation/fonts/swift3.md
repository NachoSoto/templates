## Template Information

| Name      | Description       |
| --------- | ----------------- |
| File name | fonts/swift3.stencil |
| Invocation example | `swiftgen fonts -t swift3 …` |
| Language | Swift 3 |
| Author | Olivier Halligon |

## When to use it

- When you need to generate *Swift 3* code

## Customization

You can customize some elements of this template by overriding the following parameters when invoking `swiftgen` in the command line, using `--param <paramName>=<newValue>`

| Parameter Name | Default Value | Description |
| -------------- | ------------- | ----------- |
| `enumName` | `FontFamily` | Allows you to change the name of the generated `enum` containing all font families. |

## Generated Code

**Extract:**

```swift
enum FontFamily {
  enum SFNSDisplay {
    static let black = FontConvertible(name: ".SFNSDisplay-Black", family: ".SF NS Display", path: "SFNSDisplay-Black.otf")
    static let bold = FontConvertible(name: ".SFNSDisplay-Bold", family: ".SF NS Display", path: "SFNSDisplay-Bold.otf")
    static let heavy = FontConvertible(name: ".SFNSDisplay-Heavy", family: ".SF NS Display", path: "SFNSDisplay-Heavy.otf")
    static let regular = FontConvertible(name: ".SFNSDisplay-Regular", family: ".SF NS Display", path: "SFNSDisplay-Regular.otf")
  }
  enum ZapfDingbats {
    static let regular = FontConvertible(name: "ZapfDingbatsITC", family: "Zapf Dingbats", path: "ZapfDingbats.ttf")
  }
}
```

[Full generated code](https://github.com/SwiftGen/templates/blob/master/Tests/Expected/Fonts/swift3-context-defaults.swift)

## Usage example

```swift
// You can create fonts with the convenience constructor like this:
let displayRegular = UIFont(font: FontFamily.SFNSDisplay.regular, size: 20.0)
let dingbats = UIFont(font: FontFamily.ZapfDingbats.regular, size: 20.0)

// Or as an alternative, you can refer to enum instance and call .font on it:
let sameDisplayRegular = FontFamily.SFNSDisplay.regular.font(size: 20.0)
let sameDingbats = FontFamily.ZapfDingbats.regular.font(size: 20.0)
```
