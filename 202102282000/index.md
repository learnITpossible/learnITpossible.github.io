# 【Go 学习笔记】Go 环境搭建


<!--more-->

系统：Mac

## 1. 配置环境

使用 homebrew 安装：

`brew install go`

go 1.8 版本之后不用额外配置 GOPATH、PATH，会默认设置，使用

`go dev`

查看默认环境配置；安装完成后运行如下命令进行验证：

`go version`

## 2. 安装 IDE

下载 GoLand，不要到网上找各种破解方法，直接上淘宝买一个账号，注册。

## 3. Hello World！

使用 GoLand 新建 Project（不需要一定建在 GOPATH 下），例如：demo；再在 demo 下新建目录 src；
然后新建文件 hello_world.go，输入以下代码：

```go
package main

import "fmt"

func main() {
	fmt.Println("Hello World!")
}
```

GoLand 中直接运行，或者到 src 目录下运行

`go run hello_world.go`

