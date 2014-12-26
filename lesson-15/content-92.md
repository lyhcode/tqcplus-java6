# 類別與實例

比較類別與實例的差異：

 1. 類別變數、類別方法
 2. 實例變數、實例方法


## 執行結果

```
1
2
3
4
```

## 程式碼

Main.java

```java
class ClassA {
    static int var1 = 1;
    static int method1() {
        return 2;
    }
    
    int var2 = 3;
    int method2() {
        return 4;
    }
}

public class Main {
    public static void main(String[] args) {
        System.out.println(ClassA.var1);
        System.out.println(ClassA.method1());

        ClassA a = new ClassA();
        System.out.println(a.var2);
        System.out.println(a.method2());
    }
}

```

## 開始練習

```java
class ClassA {
    static int var1 = 1;
    static int method1() {
        return 2;
    }
    
    int var2 = 3;
    int method2() {
        return 4;
    }
}

public class Main {
    public static void main(String[] args) {
        System.out.println(________.var1);
        System.out.println(________.method1());

        ClassA a = ______________;
        System.out.println(_____.var2);
        System.out.println(_____.method2());
    }
}
```
