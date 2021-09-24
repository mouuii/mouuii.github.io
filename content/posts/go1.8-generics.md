---
title: "Go1.8generics"
date: 2021-09-24T15:26:34+08:00
draft: false
categories: golang
---
### 一、背景
为了更好地理解Robert Griesemer的讲解，这里先带着大家回顾一下Go generics技术草案演化史。
![](https://tonybai.com/wp-content/uploads/go-generics-evolution-timeline.png)

### 二、代码尝鲜
```golang
package main

import (
	"fmt"
)

// The playground now uses square brackets for type parameters. Otherwise,
// the syntax of type parameter lists matches the one of regular parameter
// lists except that all type parameters must have a name, and the type
// parameter list cannot be empty. The predeclared identifier "any" may be
// used in the position of a type parameter constraint (and only there);
// it indicates that there are no constraints.

func Print[T any](s []T) {
	for _, v := range s {
		fmt.Print(v)
	}
}

func main() {
	Print([]string{"Hello, ", "playground\n"})
	Print([]int{1,2})
}
```
