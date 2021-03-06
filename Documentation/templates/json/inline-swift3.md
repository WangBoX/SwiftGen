## Template Information

| Name      | Description       |
| --------- | ----------------- |
| File name | json/inline-swift3.stencil |
| Invocation example | `swiftgen json -t inline-swift3 …` |
| Language | Swift 3 |
| Author | David Jennes |

## When to use it

- When you need to generate *Swift 4* code.
- Embeds the data from the JSON file directly in your Swift code.

## Customization

You can customize some elements of this template by overriding the following parameters when invoking `swiftgen` in the command line, using `--param <paramName>=<newValue>`

| Parameter Name | Default Value | Description |
| -------------- | ------------- | ----------- |
| `enumName` | `JSONFiles` | Allows you to change the name of the generated `enum` containing all files. |
| `preservePath` | N/A | Setting this parameter will disable the basename filter applied to all file paths. Use this if you added your data folder as a "folder reference" in your Xcode project, making that folder hierarchy preserved once copied in the build app bundle. The path will be relative to the folder you provided to SwiftGen. |
| `publicAccess` | N/A | If set, the generated constants will be marked as `public`. Otherwise, they'll be declared `internal`. |

## Generated Code

**Extract:**

```swift
internal enum JSONFiles {
  internal enum Configuration {
    internal static let apiVersion: String = "2"
    internal static let country: Any? = nil
    internal static let environment: String = "staging"
    internal static let options: [String: Any] = ["screen-order": ["1", "2", "3"]]
  }
  internal enum GroceryList {
    internal static let items: [String] = ["Eggs", "Bread", "Milk"]
  }
  internal enum Version {
    internal static let value: String = "1.2.3.beta.4"
  }
}
```

[Full generated code](https://github.com/SwiftGen/SwiftGen/blob/master/Tests/Fixtures/Generated/JSON/inline-swift3-context-all.swift)

## Usage example

```swift
// This will be an dictionary
let foo = JSONFiles.Configuration.options

// This will be an [String]
let bar = JSONFiles.GroceryList.items
```
