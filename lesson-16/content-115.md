# ArrayList

ArrayList類別實作了List介面，List介面是Collection介面的子介面，主要增加了根據索引取得物件的方法。

ArrayList使用陣列實作List介面，所以對於快速的隨機取得物件來說，使用ArrayList可以得到較好的效能，不過在移除物件或插入物件時，ArrayList就比較慢（使用 LinkedList 在這方面就好的多）。

## 執行結果

```
i5, 25000
i5, 25000
i7, 32000

```

## 程式碼

Main.java

```java
import java.util.*;

class Computer {
    private String type;
    private int price;
    
    public Computer(String type, int price) {
        this.type = type;
        this.price = price;
    }
    
    public String getType() {
        return type;
    }
    
    public int getPrice() {
        return price;
    }
}

public class Main {
    public static void main(String[] args) {
        List<Computer> list1 = new ArrayList<Computer>();
    
        list1.add(new Computer("i5", 25000));
        list1.add(new Computer("i5", 25000));
        list1.add(new Computer("i7", 32000));
        
        for (Computer c : list1) {
            System.out.println(c.getType() + ", " + c.getPrice());
        }
    }
}

```

## 開始練習

```java
import java.util.*;

class Computer {
    private String type;
    private int price;
    
    public Computer(String type, int price) {
        this.type = type;
        this.price = price;
    }
    
    //...
}

public class Main {
    public static void main(String[] args) {
        List<Computer> list1 = /* 填空 */;
    
        list1.add(new Computer("i5", 25000));
        list1.add(/* 填空 */);
        list1.add(/* 填空 */);
        
        for (Computer c : list1) {
            System.out.println(/* 填空 */);
        }
    }
}
```
