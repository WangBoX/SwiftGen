## Template Information

| Name      | Description       |
| --------- | ----------------- |
| File name | plist/inline-swift4.stencil |
| Invocation example | `swiftgen plist -t inline-swift4 …` |
| Language | Swift 4 |
| Author | David Jennes |

## When to use it

- When you need to generate *Swift 4* code.
- Embeds the data from the Plist file directly in your Swift code.

## Customization

You can customize some elements of this template by overriding the following parameters when invoking `swiftgen` in the command line, using `--param <paramName>=<newValue>`

| Parameter Name | Default Value | Description |
| -------------- | ------------- | ----------- |
| `enumName` | `PlistFiles` | Allows you to change the name of the generated `enum` containing all files. |
| `preservePath` | N/A | Setting this parameter will disable the basename filter applied to all file paths. Use this if you added your data folder as a "folder reference" in your Xcode project, making that folder hierarchy preserved once copied in the build app bundle. The path will be relative to the folder you provided to SwiftGen. |
| `publicAccess` | N/A | If set, the generated constants will be marked as `public`. Otherwise, they'll be declared `internal`. |

## Generated Code

**Extract:**

```swift
internal enum PlistFiles {
  internal enum Configuration {
    internal static let environment: String = "development"
    internal static let options: [String: Any] = ["Animation Style": "Party Mode"]
  }
  internal enum ShoppingList {
    internal static let items: [String] = ["Eggs", "Bread", "Milk"]
  }
}
```

[Full generated code](https://github.com/SwiftGen/SwiftGen/blob/master/Tests/Fixtures/Generated/Plist/inline-swift4-context-all.swift)

## Usage example

```swift
// This will be an array
let foo = PlistFiles.ShoppingList.items

// This will be an String
let bar = PlistFiles.Configuration.environment
```
