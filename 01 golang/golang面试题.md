# 1. 通用基础

## Go语言中是如何实现继承的

在Go语言中，可以通过结构体组合来实现继承，示例如下：

```go
type People struct {
    Name string
}

// 这里Student继承了People，具有People的属性
type Student struct{
    People
    Grade int
}

```

## go struct 能不能比较

原理参考：https://cloud.tencent.com/developer/article/1825054

- 不同类型的 struct 之间不能进行比较，编译期就会报错（GoLand 会直接提示）
- 同类型的 struct 也分为两种情况
  - struct 的所有成员都是可以比较的，则该 strcut 的不同实例可以比较
  - struct 中含有不可比较的成员（如 Slice），则该 struct 不可以比较

## make和new的区别

原理参考：http://c.biancheng.net/view/5722.html

- make只能用来分配及初始化类型为 slice、map、chan 的数据。new 可以分配任意类型的数据
- new 分配返回的是指针，即类型 *Type。make 返回引用，即 Type
- new 分配的空间被清零。make 分配空间后，会进行初始化

## Go的参数是值传递还是指针传递

原理参考：https://zhuanlan.zhihu.com/p/383737884; https://segmentfault.com/a/1190000037763005

- Go中所有的参数传递都是**值传递**，拷贝的都是一个副本。
- 值传递时要么是该值的副本，要么是指针的副本（比如指向切片底层数组指针的副本）

# 2. slice

## slice和array的区别

- array的长度是固定的，而slice是可变长的
- 数组作为函数参数是值传递，而切片作为函数参数时传递的是指针（本质也是值传递，是指向底层数组指针的副本）
- 切片有一个指向底层数组的指针

## 切片的底层原理

## 切片是否是线程安全的

## 切片分配在栈上还是堆上

## 切片是怎么扩容的

## 切片用copy和左值进行初始化的区别

# 3. Map

# 4. channel

# 5. 内存管理

# 6. 并发编程

# 7. 其它