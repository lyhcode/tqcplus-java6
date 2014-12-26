# 題目三

(1)請使用前兩題的答案並以Java的抽象類別及繼承，完成以下幾個在功能上
逐步擴充的堆疊（stack）。這幾個類別的繼承結構如下：

            Stack
           /    \
    BoundStack  UnboundedStack
                   \
                  TraceUnboundedStack

(2)請寫一個 Stack 類別，Stack 提供了一個 top 方法，top 先使用 pop 傳回一個堆疊頂端的值，
再使用 push 還原該堆疊的儲存值。此外，Stack 的子類別所產生的實例都只可以存放 String。

(3)請再寫一個 TraceUnboundedStack 類別，這個類別繼承 UnboundedStack。

(4)TraceUnboundedStack的getSize方法請傳回 stack.size()後的數值。

(5)每次呼叫push方法，請先印出【Pushing: + value】，再於下方印出此value值。

(6)每次呼叫pop方法，請先印出【Poping: + value】，再於下方印出此value值。

(7)請依照練習區所提供的順序依序印出，執行結果如Screen Dump。

## 執行結果

```
Pushing: abc
Pushing: def
Pushing: ghi
Pushing: jkl
4
Poping: jkl
Pushing: jkl
jkl
Poping: jkl
jkl
Poping: ghi
ghi
Poping: def
def
false
Poping: abc
abc
true
0
Poping: null
null
```

## 程式碼

JPA06_3.java

```java
import java.util.*;

abstract class Stack extends Object {
    abstract String pop();
    abstract void push(String value);
    String top() {
        String value;
        value=this.pop();
        this.push(value);
        return value;
    }
}

class UnboundedStack extends Stack {
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
            return null;
        }
    }
}

class TraceUnboundedStack extends UnboundedStack {
    int size = 0;
    int getSize() {
        return size;
    }

    void push(String value) {
        System.out.println("Pushing: " + value);
        size++;
        super.push(value);
    }

    String pop() {
        String value = super.pop();
        if (value != null) size--;
        System.out.println("Poping: " + value);
        return value;
    }
}

public class JPA06_3 {
    public static void main(String args[]) {
        TraceUnboundedStack s2 = new TraceUnboundedStack();
        s2.push("abc");
        s2.push("def");
        s2.push("ghi");
        s2.push("jkl");
        System.out.println(s2.getSize());
        System.out.println(s2.top());
        System.out.println(s2.pop());
        System.out.println(s2.pop());
        System.out.println(s2.pop());
        System.out.println(s2.empty());
        System.out.println(s2.pop());
        System.out.println(s2.empty());
        System.out.println(s2.getSize());
        System.out.println(s2.pop());
    }
}
```

## 開始練習

```java
...

public class JPD06_3 {
    public static void main(String args[]) {
        TraceUnboundedStack s2 = new TraceUnboundedStack();
        s2.push("abc");
        s2.push("def");
        s2.push("ghi");
        s2.push("jkl");
        System.out.println(s2.getSize());
        System.out.println(s2.top());
        System.out.println(s2.pop());
        System.out.println(s2.pop());
        System.out.println(s2.pop());
        System.out.println(s2.empty());
        System.out.println(s2.pop());
        System.out.println(s2.empty());
        System.out.println(s2.getSize());
    }
}
```
