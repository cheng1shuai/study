# 	Integer

## 1.构造方法

## 2.成员变量和内部类

## 3.重要方法

```
static String toString(int i, int radix) -- 将10进制数字转化为radix进制的字符串

static String toString(int i) -- 将int转换成string

static int parseInt(String s) -- 将数字字符串转换成int类型的10进制数
 调用的是重载的方法,基数为10(基数的范围2-36)

装箱操作使用的是静态工厂方法valueOf(int i)
```

```
装箱和拆箱的方法:

把Integer类型的赋值给int类型，调用intValue()方法进行拆箱赋值。
把int类型赋值给Integer，会调用valueOf()方法对int进行装箱赋值。

拆箱:intvalue	-- 返回的value是final int value; Integer对象的值在定义之后就已经确定了,不能被更改.

public int intValue() {
    return value;
}

装箱:valueOf
public static Integer valueOf(int i) {
    if (i >= IntegerCache.low && i <= IntegerCache.high)
        return IntegerCache.cache[i + (-IntegerCache.low)];
    return new Integer(i);
}
在[-128, 127] 之间的数据会被缓存下来
例题:
Integer a = 100, b = 100, c = 150, d = 150;
Long e = 150l;
System.out.println(a == b);			true	-- 缓存	
System.out.println(c == d);			false	-- 超过缓存范围	
System.out.println(c.equals(d));	true	--  拆箱进行比较,比较值	
System.out.println(d.equals(e));	false	--  类型不同
System.out.println(e.equals(d));	false	--  类型不同

public boolean equals(Object obj) {
    if (obj instanceof Integer) {
        return value == ((Integer)obj).intValue();
    }
    return false;
}

```



## 4.源码收获

```
返回String的时候,先创建一个char[] 算出长度,在使用
new String(char[]) 创建成一个字符串.

char[] buf = new char[size];
getChars(i, size, buf);
return new String(buf, true);
```



## 5.其它