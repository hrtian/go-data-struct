# Golang Data Struct

### 2. 链表

链表是一种链式存储的线性表，所有元素的`内存地址不一定是连续的`；

#### 2.1 单向链表

> ⭐ 单链表的结构和构造方法：**
>
> ```go
> // define node
> type Node struct {
>     Val interface{}
>     Next *Node
> }
> 
> // define singal linked List
> type SLL struct {
>     Size int
>     first *Node
> }
> 
> // SSL constructed function
> func newSSL() *SSL {
>     list := new(SLL)
>     list.first = &Node{
>          Val : nil,
>          Next: nil
>      }
>      return list
> }
> ```
>
> **⭐ 单链表的常用方法：**
>
> 



#### 2.2 双向链表

>   **⭐ 单链表的结构和构造方法：**
>
>   ```go
>   type DNode struct{
>       Val interface{}
>       prev *DNode
>       Next *DNode
>   }
>   
>   type DLL struct {
>       Size int
>       first *DNode
>       last *DNode
>   }
>   
>   func newDLL() *DLL {
>       list = new(DLL)
>       list.first = &DNode{
>           Val: nil,
>           Prev: nil,
>           Next: nil,
>       }
>       return list
>   }
>   ```
>
>   



*   双向链表 VS 动态数组

    动态数组：开辟、销毁内存空间的次数相对较少，但可能造成内存空间浪费（可以通过缩容解决）

    双向链表：开辟、销毁内存空间的次数相对较多，但不会造成内存空间的浪费

*   数据结构的选取

    如果频繁在==尾部==进行添加、删除操作，==动态数组、双向链表==均可选择
    如果频繁在==头部==进行添加、删除操作，建议选择使用==双向链表==
    如果有频繁的（在==任意位置==）添加、删除操作，建议选择使用==双向链表==
    如果有频繁的==查询操作==（随机访问操作），建议选择使用==动态数组==

*   有了双向链表，单向链表是否就没有任何用处了？

    并非如此，在哈希表的设计中就用到了单链表