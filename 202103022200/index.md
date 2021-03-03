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

## 映射

1、map 的定义

```go
m1 := map[type]type{key:value}
m2 := map[type]type{}
m3 := make(map[type]type, capacity)
```
2、map 的访问

```go
m[key]

if v, ok := m[key]; ok {
    // do something
} else {
    // do something
}
```

当 key 不存在时，返回零值，不能通过返回 nil 判断 key 是否存在

3、遍历 map

```go
for k, v := range m {

}
```

4、使用 map 实现工厂模式

```go
func TestFactory(t *testing.T) {
   factory := map[int]func(op int) int{}
   factory[1] = func(op int) int { return op }
   factory[2] = func(op int) int { return op * op }
   factory[3] = func(op int) int { return op * op * op }
   t.Log(factory[1](2), factory[2](2), factory[3](2)) // 2 4 8
}
```

5、使用 map 实现 set

```go
func TestSet(t *testing.T) {
   mySet := map[int]bool{}
   mySet[1] = true
   mySet[2] = true
   t.Log(len(mySet)) // 2
   delete(mySet, 1)
   t.Log(len(mySet)) // 1
}
```

