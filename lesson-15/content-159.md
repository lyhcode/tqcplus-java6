# 存取實例變數

存取實例變數。

    class Dog {
        String name;
    }
    
    Dog dog1 = new Dog();
    dog1.name = "doggy";

## 執行結果

```
第一隻狗的名字是小黑
第二隻狗的名字是小黃
```

## 程式碼

Main.java

```java
class Dog {
    String name; 
}

public class Main {
    public static void main(String[] args) {
        Dog dog1 = new Dog();
        dog1.name = "小黑";
        
        Dog dog2 = new Dog();
        dog2.name = "小黃";
        
        System.out.println("第一隻狗的名字是" + dog1.name);
        System.out.println("第二隻狗的名字是" + dog2.name);
    }
}

```

## 開始練習

```java
class Dog {
    /* 定義實例變數 */
}

public class Main {
    public static void main(String[] args) {
        Dog dog1 = new Dog();
        dog1._____________;
        
        Dog dog2 = ________________;
        dog2._____________;
        
        System.out.println("第一隻狗的名字是" + dog1.name);
        System.out.println(___________________________);
    }
}
```
