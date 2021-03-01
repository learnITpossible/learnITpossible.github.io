# 【Go 学习笔记】基本程序结构


<!--more-->

## 变量、常量

### 变量定义

方式一：

```go
var a int = 1
var b = 1

var a, b = 1, 1
```

方式二：

```go
var (
    a int = 1
    b = 1
)
```

方式三：

```go
a := 1
b := 1

a, b := 1, 1
```

### 语法糖

交换两个数

```go
a, b = b, a
```

### 常量定义

连续常量定义

```go
const (
    Monday = iota + 1
    Tuesday
    Wednesday
    Thursday
    Friday
    Saturday
    Sunday
)
```

则 Monday 到 Sunday 的值分别为 1 到 7

## 数据类型

### 基本数据类型

```go
bool

string

int int8 int16 int32 int64

uint uint8 uint16 uint32 uint64 uintptr

byte // alias of int8

rune // alias of int32

float32 float64

complex64 complex128
```

### 类型转换

不支持隐式类型转换

### string

`string` 类型的默认值为空字符串，不是 `nil`

## 运算符

### 算术运算符

没有 `++i、--i`

### 比较运算符

`==` 可以比较数组，前提是数组长度一致

### 逻辑运算符

### 位运算符

`&^` 按位清零，可以理解为 `&` 与 `^` 的组合

## 条件和循环

### for

Go 只有 `for` 一种循环；`for condition` 相当于其他语言的 `while(confition)`

### if

支持变量赋值

### switch

条件表达式不限制为常量或整数

单个 `case` 中，可以出现多个结果选项，用逗号分开

不需要 `break` 语句

可以不设定 `switch` 后的条件表达式，这种情况下，与多个 `if...else...` 的逻辑相同

