# Getter 與 Setter

請動手完成以下練習，使用 Setter 改變實例變數的內容。

## 執行結果

```
bible
```

## 程式碼

Main.java

```java
class Book {
    String name;
    
    public void setName(String name) {
        this.name = name;
    }
    
    public String getName() {
        return name;
    }
}

public class Main {
    public static void main(String[] args) {
        Book book1 = new Book();
        book1.setName("bible");
		System.out.println(book1.getName());        
    }
}
```

## 開始練習

```java
class Book {
    String name;
    
    public void setName(String name) {
        _________________;
    }
    
    public String getName() {
        return name;
    }
}

public class Main {
    public static void main(String[] args) {
        Book book1 = new Book();
        book1._______________;
		System.out.println(book1.getName());        
    }
}```
