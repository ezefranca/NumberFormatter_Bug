# NumberFormatter_Bug
NumberFormatter Bug

## RDAR: FB11978348

### Unexpected Return from NumberFormatter with bad formatted strings.


## Basic information
Please provide a descriptive title for your feedback:
Unexpected Return from NumberFormatter with bad formatted strings.
## Which area are you seeing an issue with?
Swift Compiler

## What type of feedback are you reporting?
Incorrect/Unexpected Behavior

## Description
Please describe the issue:

NumberFormatter return different values, depending with you are using a real device or a simulator. On simulator it's ignores bad formatted strings (With spaces in the beginning). On a real device it's not happen.
Please list the steps you took to reproduce the issue:

```swift
func toDouble(value: String) -> Double? { 
return NumberFormatter().number(from: value)?.doubleValue 
} 
```

To test use for example: " -9.34" (there is a space before the minus) On a simulator the value " -9.34" returns 9.34, even with the space in the beginning. - On a real device it's returns nil.

## What did you expect to happen?
Always returns nil.

## What actually happened?
On simulator returned the -9.34 for example to " -9.34" On a real device returned nil
