# 題目一

(1)請使用陣列寫一個 BoundStack 類別。

(2)在宣告時便需要指定一個 BoundStack 堆疊的大小

(3)BoundStack 有三個方法：push(存入堆疊資料)、pop(從堆疊中取出資料) 及測試一個 BoundStack 實例是否是空的 empty 方法(Boolean 值)。

(4)在 push 方法中，若判斷已超出堆疊最大容量，則顯示【stack-overflow】。

(5)在pop方法中，若堆疊區為空值，則顯示【stack-is-empty】。

(6)在測試是否為空值的方法，若為空值，請傳回【true】，否則傳回【false】。

(7)請依照右邊練習區所提供的順序印出，顯示結果如Screen Dump。

## 執行結果

```
stack-overflow
ghi
def
abc
true
```

## 程式碼

JPA06_1.java

```java
class BoundStack {
    int maxSize = 0;
    int s_top = -1;
    String[] stack;
    
    BoundStack(int a) {
        maxSize = a;
        stack = new String[a];
    }
    
    void push(String value) {
        if (s_top < maxSize - 1) {
            s_top = s_top + 1;            
            stack[s_top] = value;
           
        } else {
            System.out.println("stack-overflow");
        }
    }
    
    String pop() {
        String topValue;
        if (s_top >= 0) {
            topValue = stack[s_top];
            s_top = s_top - 1;
        } else {
            topValue = "stack-is-empty";
        }
        return topValue;
    }
    
    boolean empty() {
        return (s_top == -1) ? true : false;
    }
}

public class JPA06_1 {
    public static void main(String args[]) {
        BoundStack s = new BoundStack(3);
        s.push("abc");
        s.push("def");
        s.push("ghi");
        s.push("jkl");
        
        System.out.println(s.pop());
        System.out.println(s.pop());
        System.out.println(s.pop());
        System.out.println(s.empty());
    }
}
```

## 開始練習

```java
...

public class JPD06_1 {
    public static void main(String args[]) {
        BoundStack s = new BoundStack(3);
        s.push("abc");
        s.push("def");
        s.push("ghi");
        s.push("jkl");
        
        System.out.println(s.pop());
        System.out.println(s.pop());
        System.out.println(s.pop());
        System.out.println(s.empty());
    }
}
```
