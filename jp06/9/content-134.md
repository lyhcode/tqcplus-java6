# 題目四

(1)請將 Stack 及 UnboundedStack 類別以 generic 的方式改寫，使得 UnboundedStack 能產生可以儲存數字的實例，也可以產生能儲存 String 的實例等等。

(2)請依照練習區所提供的順序依序印出，執行結果如Screen Dump。

## 執行結果

```
ghi
ghi
2
abc
null
```

## 程式碼

JPA06_4.java

```java
import java.util.*;
abstract class Stack<T> {
    abstract T pop();
    abstract void push(T value);
    T top() {
        T value;
        value=this.pop();
        this.push(value);
        return value;
      }
}
    
class UnboundedStack<T> extends Stack<T> {
    LinkedList stack = new LinkedList<T>();

    boolean empty() {
        return (stack.size() == 0) ? true : false;
    }
    void push(T value) {  
        stack.addFirst(value);
    }    
    T pop() { 
        if (!(this.empty())) {
            T topValue = (T)stack.getFirst();
            stack.removeFirst();
            return topValue;
         } else {
            return null;
         }
    }
}

public class JPA06_4 {
    public static void main(String args[]) {
        UnboundedStack s = new UnboundedStack();
        s.push("abc");    s.push(2);    s.push("ghi");
        System.out.println(s.top());
        System.out.println(s.pop());
        System.out.println(s.pop());
        System.out.println(s.pop());
        System.out.println(s.pop());
    }
}
```

## 開始練習

```java
...

public class JPD06_4 {
    public static void main(String args[]) {
        UnboundedStack s = new UnboundedStack();
        s.push("abc");    s.push(2);    s.push("ghi");
        System.out.println(s.top());
        System.out.println(s.pop());
        System.out.println(s.pop());
        System.out.println(s.pop());
        System.out.println(s.pop());
    }
}
```
