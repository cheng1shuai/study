# 	Collections

## 1.构造方法

```
private Collections() {
}
```



## 2.成员变量和内部类

## 3.重要方法

```
static void shuffle(List<?> list){} 打乱集合顺序
底层实现,继承容量大于5个的时候使用数组进行随机交换,小于5个的时候用集合进行交换


if (size < SHUFFLE_THRESHOLD || list instanceof RandomAccess) {
    for (int i=size; i>1; i--)
        swap(list, i-1, rnd.nextInt(i));
} else {
    Object arr[] = list.toArray();

    // Shuffle array
    for (int i=size; i>1; i--)
        swap(arr, i-1, rnd.nextInt(i));

    // Dump array back into list
    // instead of using a raw type here, it's possible to capture
    // the wildcard but it will require a call to a supplementary
    // private method
    ListIterator it = list.listIterator();
    for (int i=0; i<arr.length; i++) {
        it.next();
        it.set(arr[i]);
    }
}

private static void swap(Object[] arr, int i, int j) {
    Object tmp = arr[i];
    arr[i] = arr[j];
    arr[j] = tmp;
}
public static void swap(List<?> list, int i, int j) {
    // instead of using a raw type here, it's possible to capture
    // the wildcard but it will require a call to a supplementary
    // private method
    final List l = list;
    l.set(i, l.set(j, l.get(i)));
}
```



## 4.源码收获

## 5.其它