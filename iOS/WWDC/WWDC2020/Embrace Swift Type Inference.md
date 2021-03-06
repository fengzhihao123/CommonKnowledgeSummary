### 活用 Swift 类型推断
* 类型推断的工作机制
```
let x = ""
//虽然代码中没有显式的写出 x 的类型，但 compile 可以通过类型推断算法将其补全为下面的代码。
let x: String = ""
```
* compiler 如何自动捕获代码中的错误
    - 记录源码中的错误信息。
    - 尝试去修复错误一遍继续类型推断算法。
    - 基于收集的信息来提供有用的错误信息。
* 类型推断就像拼图，一块一块的拼完整。
* 显示当前错误信息：
    - Xcode -> Behaviors -> Edit Behaviors -> Fails -> 选中 [Show] Navigator [Current]

* 对于复杂的类型推断编译器是如何替换的：
    - Before
    ![image](https://github.com/fengzhihao123/FZHBlog/blob/master/images/embrace_swift_type_inference_before.png "类型推断前")
    - After
    ![image](https://github.com/fengzhihao123/FZHBlog/blob/master/images/embrace_swift_type_inference_after.png "类型推断后")
* 类型推断的好处：
    - 代码更加简洁、易读。
    - 编码更加简单、高效。
