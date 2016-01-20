# 題目二

(1)請使用 LinkedList 寫一個 UnboundedStack 類別。

(2)UnboundedStack 有三個方法：push(存入堆疊資料)、pop(從堆疊中取出資料) 及測試一個 UnboundStack 實例是否是空值的 empty 方法(Boolean 值)。

(3)在pop方法中，若堆疊區為空值，則顯示【Stack is empty!】。

(4)在測試是否為空值的方法，若為空值，請傳回【true】，否則傳回【false】。

(5)請依照練習區所提供的順序依序印出，執行結果如Screen Dump。

## 執行結果

```
jkl
ghi
def
false
abc
true
```

## 程式碼

JPA06_2.java

```java
import java.util.*;

class UnboundedStack {
    LinkedList<String> stack = new LinkedList<String>();
    boolean empty() {
        return (stack.size() == 0) ? true : false;
    }

    void push(String arg) {
        stack.addFirst(arg);  
    }  

    String pop() {
        if (!(this.empty())) {
            String topValue = stack.getFirst();
            stack.removeFirst();
            return topValue;
        } else {
            return "Stack is empty!";
        }
    }
}

public class JPA06_2 {
    public static void main(String args[]) {
        UnboundedStack s = new UnboundedStack();
        s.push("abc");
        s.push("def");
        s.push("ghi");
        s.push("jkl");

        System.out.println(s.pop());
        System.out.println(s.pop());
        System.out.println(s.pop());
        System.out.println(s.empty());
        System.out.println(s.pop());
        System.out.println(s.empty());
    }
}
```

## 開始練習

```java
...

public class JPD06_2 {
    public static void main(String args[]) {
        UnboundedStack s = new UnboundedStack();
        s.push("abc");
        s.push("def");
        s.push("ghi");
        s.push("jkl");

        System.out.println(s.pop());
        System.out.println(s.pop());
        System.out.println(s.pop());
        System.out.println(s.empty());
        System.out.println(s.pop());
        System.out.println(s.empty());
    }
}
```
