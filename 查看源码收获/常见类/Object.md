# 	Object

## 1.构造方法

```
是所有类的顶级父类
```

## 2.成员变量和内部类

## 3.重要方法

```
equals方法	最终采用的是 == 比较地址值.
equals(Object obj) {
    return (this == obj);
}
```

```
clone() 方法
----------不知道是干什么的
```

```
toString方法 -- 直接输出引用对象,默认调用的是该对象的toString方法
输出的是 全类名+ @ + hash值
    public String toString() {
        return getClass().getName() + "@" + Integer.toHexString(hashCode());
    }
```

```
线程安全相关的方法
public final native void notify();
public final native void notifyAll();

public final native void wait(long timeout) throws InterruptedException;
public final void wait(long timeout, int nanos) throws InterruptedException 
	timeout是秒为单位 nanos是微妙为单位
public final void wait() throws InterruptedException

```

```
GC相关的方法
protected void finalize() throws Throwable { }
```



## 4.源码收获

## 5.其它