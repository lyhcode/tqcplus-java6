# 產生實例

利用 **new** 關鍵字，將已經定義的類別產生新的實例（instance）。

## 執行結果

```
已經產生 dog1, dog2, cat1 三個實例
```

## 程式碼

Main.java

```java
class Dog {
    //狗的類別
}

class Cat {
    //貓的類別
}

public class Main {
    public static void main(String[] args) {
        Dog dog1 = new Dog();
        Dog dog2 = new Dog();
        Cat cat1 = new Cat();
        
        System.out.println("已經產生 dog1, dog2, cat1 三個實例");
    }
}

```

## 開始練習

```java
class Dog {
    //狗的類別
}

__________ Cat {
    //貓的類別
}

public class Main {
    public static void main(String[] args) {
        Dog dog1 = __________;
        _____ dog2 = new Dog();
        Cat cat1 = __________;
        
        System.out.println("已經產生 dog1, dog2, cat1 三個實例");
    }
}
```
