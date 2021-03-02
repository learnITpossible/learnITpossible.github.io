# 【Go 学习笔记】常用集合


<!--more-->

## 数组和切片

### 数组

数组定义时必须指定长度

```go
var arr = [4]int{1, 2, 3, 4}
arr = [...]int{1, 2, 3}
```

### 切片

切片是一个结构体

```go
type slice struct {
   array unsafe.Pointer
   len   int
   cap   int
}
```

Pointer 指向底层数组的特定位置，len 是切片的长度，cap 是 Pointer 指向底层数组的位置到数组末尾的长度。

```go
var slice = []int{1, 2, 3, 4}
slice = make([]int, 3, 5)
slice = append(slice, 1, 2, 3)

slice = slice[1:2]
```

