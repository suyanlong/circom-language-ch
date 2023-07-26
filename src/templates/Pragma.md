# 编译指示

## 版本编译指示

所有具有 .circom 扩展名的文件都应以pragma指定编译器版本的第一条指令开头，如下所示：

```rust
pragma circom xx.yy.zz;
```

这是为了确保电路与指令后指示的编译器版本兼容pragma。否则，编译器会抛出警告。

如果文件不包含此指令，则假定该代码与最新编译器版本兼容，并抛出警告。

## 自定义模板编译指示

从 circom 2.0.6 开始，该语言允许定义自定义模板（有关更多信息，请参阅此）。此编译指示允许 circom 程序员轻松判断它是否使用自定义模板：如果任何声明自定义模板的文件或包含声明任何自定义模板的文件不使用此编译指示，编译器将产生错误。此外，它还会通知程序员哪些文件应包含此编译指示。

要使用它，只需在需要在.circom文件的开头（以及版本编译指示之后）添加以下指令：

```rust
pragma custom_templates;
```