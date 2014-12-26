# private 與 protected

這個程式碼存在一些錯誤造成無法編譯，請先瞭解 private 與 protected 的規則，並利用**註解**將可能產生錯誤的地方消除。

    System.out.println(...);

加上註解：

    //System.out.println(...);



## 執行結果

```
2
3
2
3
5
2
3
5
```

## 程式碼

Main.java

```java
class A {
    private int var1 = 1;
    protected int var2 = 2;

    private int method1() {
        return var1;
    }

    protected int method2() {
        return var2;
    }

    protected int method3() {
        return method1() + method2();
    }
}

class B extends A {
    int method4() {
        return method2() + method3();
    }
}

class C extends A {
    int method5() {
        return method2() + method3();
    }
}

public class Main {
    public static void main(String[] args) {
        A a = new A();
        B b = new B();
        C c = new C();

        //System.out.println(a.method1());
        System.out.println(a.method2());
        System.out.println(a.method3());

        //System.out.println(b.method1());
        System.out.println(b.method2());
        System.out.println(b.method3());
        System.out.println(b.method4());

        //System.out.println(c.method1());
        System.out.println(c.method2());
        System.out.println(c.method3());
        //System.out.println(c.method4());
        System.out.println(c.method5());
    }
}

```

## 開始練習

```java
class A {
    private int var1 = 1;
    protected int var2 = 2;

    private int method1() {
        return var1;
    }

    protected int method2() {
        return var2;
    }

    protected int method3() {
        return method1() + method2();
    }
}

class B extends A {
    int method4() {
        return method2() + method3();
    }
}

class C extends A {
    int method5() {
        return method2() + method3();
    }
}

public class Main {
    public static void main(String[] args) {
        A a = new A();
        B b = new B();
        C c = new C();

        System.out.println(a.method1());
        System.out.println(a.method2());
        System.out.println(a.method3());

        System.out.println(b.method1());
        System.out.println(b.method2());
        System.out.println(b.method3());
        System.out.println(b.method4());

        System.out.println(c.method1());
        System.out.println(c.method2());
        System.out.println(c.method3());
        System.out.println(c.method4());
        System.out.println(c.method5());
    }
}
```
