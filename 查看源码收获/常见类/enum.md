# 	enum

## 1.定义枚举类

1.在IDEA中定义枚举类,newClass 类型选择为enum

```
public enum User {
    XM,LL,TM,LX
}
```

2.使用

```
public static void main(String[] args) {
    System.out.println(User.XM);
}
```

## 2.带数据的枚举

```
定义枚举类: 不需要提供set方法
public enum User {
    XM("小明",18),
    LL("莉莉", 19),
    PH("胖虎",20);

    private String username;
    private Integer age;

    User(String username, Integer age) {
        this.username = username;
        this.age = age;
    }

    public String getUsername() {
        return username;
    }

    public Integer getAge() {
        return age;
    }
}

通过get方法使用:
public static void main(String[] args) {
    System.out.println(User.XM.getUsername());
    System.out.println(User.XM.getAge());
}
```



## 3.通过枚举值获取对应的枚举项

```
使用的是上面定义的枚举类
User user1 = User.valueOf(User.class, "XM");
User user2 = User.valueOf("XM");
拿到的是具体的枚举项,使用getXXX方法可以获取具体的值.
```



## 

## 