---
layout: post
title: Go常用
categories: [Go常用]
description: Go常用
keywords: Go常用
---

# Go常用语法

#### Go切片

> go中的动态数组，他会在容量不足时自动扩容。源码位于 `cmd/compile/internal/types.NewSlice`

**数据结构**

- Data 指向数组的指针
- Len 当前切片的长度
- Cap 当前切片的容量



#### Go chan

```go
ch1 := make(chan struct{})

<-ch1

priority:
			for {
				select {
				case val1 := <-ch1:
					fmt.Println(val1)
				default:
					break priority
				}
			}
		}
```



#### Go build

```sh
#逃逸 逃逸分析
go build -gcflags '-m -m -l' xxx.go

```

![](https://raw.githubusercontent.com/zhiming1/blog_pictures/main/blog/img202312092214825.png)