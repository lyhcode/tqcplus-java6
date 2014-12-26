# 實例變數

在一個貓的類別「Cat」，定義一個實例變數「name」用來儲存貓的「名字」：

    class Cat {
        String name = "Miou";
    }

產生一個貓的實例，並將貓的名字顯示出來：

    Cat cat1 = new Cat();
    System.out.println(cat1.name);

在閱讀實例的說明後，請動手完成以下練習。

## 執行結果

```
賈伯斯傳
```

## 程式碼

Main.java

```java
class Book {
    String name = "賈伯斯傳";
}

public class Main {
    public static void main(String[] args) {
        Book book1 = new Book();
        System.out.println(book1.name);
    }
}

```

## 開始練習

```java
class Book {
    String name = "____________";
}

public class Main {
    public static void main(String[] args) {
        Book book1 = _________________;
		System.out.println(book1._____);        
    }
}
```
