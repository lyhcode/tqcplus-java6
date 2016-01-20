# 題目五

(1)請為上一題增加例外處理的功能，使得 pop 一個空的堆疊時，可以印出【Stack is empty!】。

## 執行結果

```
ghi
ghi
2
abc
Stack is empty!
```

## 程式碼

JPA06_5.java

```java
import java.util.*;

abstract class Stack<T> {
    abstract T pop() throws Exception;
    abstract void push(T value);
    T top() throws Exception {
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
    T pop() throws Exception { 
        if (!(this.empty())) {
            T topValue = (T)stack.getFirst();
            stack.removeFirst();
            return topValue;
         } else {
            throw (new Exception("Stack is empty!"));
         }
    }
}

public class JPA06_5 {
    public static void main(String args[]) {
        try {
            UnboundedStack s = new UnboundedStack();
            s.push("abc");    s.push(2);    s.push("ghi");
            System.out.println(s.top());
            System.out.println(s.pop());
            System.out.println(s.pop());
            System.out.println(s.pop());
            System.out.println(s.pop());
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

## 開始練習

```java
...

public class JPD06_5 {
    public static void main(String args[]) {
        try {
            UnboundedStack s = new UnboundedStack();
            s.push("abc");    s.push(2);    s.push("ghi");
            System.out.println(s.top());
            System.out.println(s.pop());
            System.out.println(s.pop());
            System.out.println(s.pop());
            System.out.println(s.pop());
        } ...
        ...
    }
}
```
