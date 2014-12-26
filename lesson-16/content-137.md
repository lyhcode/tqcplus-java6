# Map

Map interfaces

    java.util.Map

Implementing classes

    java.util.HashMap
    java.util.LinkedHashMap
    java.util.TreeMap

## 執行結果

```
true
true
false
jacky = 22000
john = 30000
jacky = 22000
john = 30000

```

## 程式碼

Main.java

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Map<String, Integer> salary;
        
        salary = new HashMap<String, Integer>();
        
        salary.put("john", 30000);
        salary.put("jacky", 22000);
        
        System.out.println(salary.containsKey("john"));
        System.out.println(salary.containsKey("jacky"));
        System.out.println(salary.containsKey("mary"));
        
        Iterator it = salary.entrySet().iterator();
        while (it.hasNext()) {
            Map.Entry pairs = (Map.Entry)it.next();
            System.out.println(pairs.getKey() + " = " + pairs.getValue());
        }
        
        for (String key : salary.keySet()) {
            System.out.println(key + " = " + salary.get(key));
        }
    }
}

```

## 開始練習

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Map<String, Integer> salary;
        
        salary = new HashMap<__________, __________>();
        
        salary.put("john", 30000);
        salary.put("jacky", _________);
        
        System.out.println(salary.containsKey("john"));
        System.out.println(salary.containsKey("jacky"));
        System.out.println(salary.containsKey("mary"));
        
        Iterator it = salary.entrySet().iterator();
        while (it.hasNext()) {
            Map.Entry pairs = (Map.Entry)it.next();
            System.out.println(pairs.getKey() + " = " + pairs.getValue());
        }
        
        for (String key : salary.____________) {
            System.out.println(key + " = " + ____________);
        }
    }
}
```
