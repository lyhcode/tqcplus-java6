# 實例方法

範例：定義實例方法。

    class Dog {
        void walk() {
            System.out.println("狗在走路");
        }
    }

練習：

撰寫一個產生貓與狗的程式，利用實例方法讓貓與狗有不同叫聲。

## 執行結果

```
汪～汪～
喵～嗚～
```

## 程式碼

Main.java

```java
class Dog {
    void bark() {
        System.out.println("汪～汪～");
    }
}

class Cat {
    void bark() {
        System.out.println("喵～嗚～");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog1 = new Dog();
        dog1.bark();
        
        Cat cat1 = new Cat();
        cat1.bark();
    }
}

```

## 開始練習

```java
class Dog {
    void bark() {
        System.out.println(_____________);
    }
}

class Cat {
    /* 定義實例方法 */
}

public class Main {
    public static void main(String[] args) {
        Dog dog1 = new Dog();
        dog1.bark();
        
        Cat cat1 = ____________;
        cat1.____________;
    }
}
```
