# 建構子（constructor）

完成練習題的建構子實作程式碼。

## 執行結果

```
cat1 is 小黃
cat2 is 小黑
```

## 程式碼

Main.java

```java
class Animal {
    String name;

    public String getName() {
        return name;
    }
}

class Cat extends Animal {
    public Cat(String name) {
        this.name = name;
    }
}

public class Main {
    public static void main(String[] args) {
        Cat cat1 = new Cat("小黃");
        Cat cat2 = new Cat("小黑");

        System.out.println("cat1 is " + cat1.getName());
        System.out.println("cat2 is " + cat2.getName());
    }
}

```

## 開始練習

```java
class Animal {
    String name;

    public String getName() {
        return name;
    }
}

class Cat extends Animal {
    public Cat(________) {
        //...
    }
}

public class Main {
    public static void main(String[] args) {
        Cat cat1 = new Cat("小黃");
        Cat cat2 = new Cat("小黑");

        System.out.println("cat1 is " + cat1.getName());
        System.out.println("cat2 is " + cat2.getName());
    }
}
```
