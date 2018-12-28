# 	StringBuilder

## 1.构造方法

```
StringBuffer() {
        super(16);
    }
创建默认大小为16的可变字符串缓冲池


public StringBuffer(int capacity) {
        super(capacity);
    }
    
创建指定初始大小的字符串缓冲池

public StringBuffer(String str) {
        super(str.length() + 16);
        append(str);
    }
创建比指定字符串大16的字符串缓冲区

```



## 2.成员变量和内部类class StringBuffer	extends AbstractStringBuilder;

扩容的方法是AbstractStringBuilder中定义的,扩容的是原来的两倍.

String toString() 	将当前StringBuilder对象转换为String对象。

## 3.重要方法

```
int length(): 返回字符串的长度

int capacity(): 返回字符数组的大小

StringBuffer append(StringBuffer sb): 将元素添加到字符串缓冲区的后面

扩容的方法:
class StringBuffer	extends AbstractStringBuilder;
扩容的方法是AbstractStringBuilder中定义的,扩容的是原来的两倍.

String toString() 	将当前StringBuilder对象转换为String对象。
```



## 4.源码收获

## 5.其它