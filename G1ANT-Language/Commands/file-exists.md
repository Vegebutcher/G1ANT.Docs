# file.exists

**Syntax:**

```G1ANT
file.exists  filename ‴‴  
```

**Description:**

Command `file.exists` allows to determine whether the specified file exists. It waits given timeout and when the expected file does not appear, it jumps to the defined label or stops the process.

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`filename`| [string](https://github.com/G1ANT-Robot/G1ANT.Manual/blob/master/G1ANT-Language/Structures/string.md) | yes |  | path and filename of the expected file |
|`if`| [bool](https://github.com/G1ANT-Robot/G1ANT.Manual/blob/master/G1ANT-Language/Structures/bool.md) | no | true | runs the command only if condition is true |
|`timeout`| [variable](https://github.com/G1ANT-Robot/G1ANT.Manual/blob/master/G1ANT-Language/Special-Characters/variable.md) | no | [♥timeoutcommand](https://github.com/G1ANT-Robot/G1ANT.Manual/blob/master/G1ANT-Language/Variables/Special-Variables.md)  | specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
|`errorjump` | [label](https://github.com/G1ANT-Robot/G1ANT.Manual/blob/master/G1ANT-Language/Structures/label.md) | no | | name of the label to jump to if given `timeout` expires |
|`errormessage`| [string](https://github.com/G1ANT-Robot/G1ANT.Manual/blob/master/G1ANT-Language/Structures/string.md) | no |  | message that will be shown in case error occurs and no `errorjump` argument is specified |

For more information about `if`, `timeout`, `errorjump` and `errormessage` arguments, please visit [Common Arguments](https://github.com/G1ANT-Robot/G1ANT.Manual/blob/master/G1ANT-Language/Common-Arguments.md)  manual page.

This command is contained in **G1ANT.Language.dll**.

**Example 1:**

This example shows how to check if expected file will appear in given timeout, if not goes to "notfound" label.

```G1ANT
file.exists filename ‴C:\Users\♥environment⟦USERNAME⟧\G1ANT\test.txt‴ timeout 1000 errorjump ➜notFound
dialog ‴File exists‴
jump ➜finish
➜notFound
dialog ‴File doesn't exist‴
➜finish 
```

When the file exists:
 
 

When the file doesn't exist and will not appear in given timeout:
 
 

**Example 2:**

```G1ANT
file.exists filename ‴C:test.txt‴ errormessage ‴Sorry, I could not find file‴
```
