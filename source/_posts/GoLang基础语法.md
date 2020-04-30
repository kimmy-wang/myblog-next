---
title: GoLang基础语法
date: 2019-03-03 20:11:52
categories:
- 编程语言
tags:
- GoLang
---

## 变量定义

### 从hello world入手

```go
package main

import "fmt"

func main() {
	fmt.Println("Hello World")
}
```

控制台输出：
```text
Hello World
```

<!--more-->

### 变量默认值
```go
package main

import "fmt"

func main() {
	var a int
	var s string
	fmt.Println(a, s)
}
```

控制台输出：
```text
0 
```
注：s为"",故打印出来没有效果

如果想让""字符串显示，则代码如下：
```go
package main

import "fmt"

func main() {
	var a int
	var s string
	fmt.Println(a, s)
	fmt.Printf("%d %q\n", a, s)
}
```

控制台输出：
注：s为"",故打印出来没有效果
```text
0 
0, ""
```

### 变量定义并初始化
#### 第一种方式
```go
package main

import "fmt"

func main() {
	var a, b int = 3, 4
	var s string = "abc"
	fmt.Println(a, b, s)
}
```

控制台输出：
```text
3 4 abc
```

#### 第二种方式
```go
package main

import "fmt"

func main() {
	var a, b, c, d = 3, 4, true, "def"
	fmt.Println(a, b, c, d)
}
```

控制台输出：
```text
3 4 true def
```

#### 第三种方式
```go
package main

import "fmt"

func main() {
	a, b, c, d := 3, 4, true, "def"
	fmt.Println(a, b, c, d)
}
```

控制台输出：
```text
3 4 true def
```

#### 如果是在包内定义变量而非func中定义变量，不能使用使用第三种方式，即不能使用:=。

代码如下：
```go
package main

import "fmt"

var wy  = 3
var wyy = 4
var ss = "3456"

func main() {
	fmt.Println(wy, wyy, ss)
}
```
还可以如下定义：
```go
package main

import "fmt"

var (
	wy  = 3
    wyy = 4
    ss = "3456"
 )

func main() {
	fmt.Println(wy, wyy, ss)
}
```

输出如下：
```text
3 4 3456
```

## 内置变量类型

```text
bool, string

加u，代表无符号整数；不加u，代表有符号整数；不规定长度，与操作系统相关
(u)int, (u)int8, (u)int16, (u)int32, (u)int64

uintptr: 无符号整型，长度与操作系统相关，用于存放一个指针, ptr代表指针类型（Pointer）

byte： 类似 uint8

rune: 字符型，4个字节， 32位二进制位，类似 int32

float32, float64

complex64: 复数：实数和虚数为32位 float32

complex128: 复数：实数和虚数为64位 float64

```

Golang中的复数
```go
package main

import (
	"fmt"
	"math/cmplx"
)

func main() {
	c := 3 + 4i
	fmt.Println(cmplx.Abs(c))
}

```

欧拉公式
```go
package main

import (
	"fmt"
	"math/cmplx"
	"math"
)

func main() {
	fmt.Println(
    		cmplx.Exp(1i * math.Pi) + 1)
}

```

控制台输出
```text
(0+1.2246467991473515e-16i)
```

### 类型转换

#### 类型转换是强制的，无隐式类型转换
勾股定理
```go
package main

import (
	"fmt"
	"math"
)

func main() {
	var a, b int = 3, 4
	fmt.Println(math.Sqrt(float64(a*a + b*b)))
}

```

控制台输出
```text
5
```
