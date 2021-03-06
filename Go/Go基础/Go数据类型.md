Go 的字符串（string）、数组和切片在底层有相同的内存结构，但上层由于语法限制会有不同的表现。



## 数组

是一种值类型，可修改，但本身赋值和函数传参都是采用整块数组复制的方式。

与 C 语言不同，Go 的数组变量表示整个数组，而不是隐式表示数组第一个元素的地址，所以如上所说，数组的复制是要整块复制。且**数组长度是数组类型的组成部分，因此指向不同长度数组的数组指针类型也不同**。





## 字符串

字符串底层对应的是字节数组，有只读属性，复制的时候只复制地址和长度。



## 切片[[参考资料]([https://www.cnblogs.com/qcrao-2018/p/10631989.html#%E5%AD%97%E9%9D%A2%E9%87%8F](https://www.cnblogs.com/qcrao-2018/p/10631989.html#字面量))]

底层结构和字符串类似，但解除了只读限制。复制过程因为每个切片都含有底层数据的指针，所以赋值和传参也是复制指针和长度。

slice 源码结构如下：

```go
// runtime/slice.go
type slice struct {
    array unsafe.Pointer // 元素指针
    len   int // 长度 
    cap   int // 容量
}
```

- `指针`，指向底层数组；
- `长度`，表示切片可用元素的个数，也就是说使用下标对 slice 的元素进行访问时，下标不能超过 slice 的长度；
- `容量`，底层数组的元素个数，容量 >= 长度。在底层数组不进行扩容的情况下，容量也是 slice 可以扩张的最大限度。