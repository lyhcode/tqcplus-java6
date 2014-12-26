# 封裝（Encapsulation）

在物件導向程式設計方法中，封裝（英语：Encapsulation）是指，一種將抽象性函式介面的實作細節部份包裝、隱藏起來的方法。同時，它也是一種防止外界呼叫端，去存取物件內部實作細節的手段，這個手段是由程式語言本身來提供的。這兩個概念有一些不同，但通常被混合使用。封裝被視為是物件導向的四項原則之一。

適當的封裝，可以將物件使用介面的程式實作部份隱藏起來，不讓使用者看到，同時確保使用者無法任意更改物件內部的重要資料。它可以讓程式碼更容易理解與維護，也加強了程式碼的安全性。

動手練習：請在 PersonC 類別的 setAge() 方法中，增加合理的年齡判斷（年齡必須介於 0 至 120 之間）。

## 執行結果

```
a 的年齡為 1000 歲
b 的年齡為 1000 歲
1000 不是合理的年齡數字
c 的年齡為 30 歲
```

## 程式碼

Main.java

```java
class PersonA {
    int age = 30;
}

class PersonB {
    private int age = 30;

    public void setAge(int age) {
        this.age = age;
    }

    public int getAge() {
        return age;
    }
}

class PersonC {
    private int age = 30;

    public void setAge(int age) {
        if (age >= 0 && age <= 120) {
            this.age = age;
        }
        else {
            System.out.println(age + " 不是合理的年齡數字");
        }
    }
    
    public int getAge() {
        return age;
    }
}


public class Main {
    public static void main(String[] args) {
        PersonA a = new PersonA();
        a.age = 1000;

        System.out.println("a 的年齡為 " + a.age + " 歲");

        PersonB b = new PersonB();
        //b.age = 900;
        b.setAge(1000);

        System.out.println("b 的年齡為 " + b.getAge() + " 歲");

        PersonC c = new PersonC();
        //c.age = 900;
        c.setAge(1000);

        System.out.println("c 的年齡為 " + c.getAge() + " 歲");
    }
}

```

## 開始練習

```java
class PersonA {
    int age = 30;
}

class PersonB {
    private int age = 30;

    public void setAge(int age) {
        this.age = age;
    }

    public int getAge() {
        return age;
    }
}

class PersonC {
    private int age = 30;

    public void setAge(int age) {
        if (_______________) {
            this.age = age;
        }
        else {
            System.out.println(age + " 不是合理的年齡數字");
        }
    }
    
    public int getAge() {
        return age;
    }
}


public class Main {
    public static void main(String[] args) {
        PersonA a = new PersonA();
        a.age = 1000;

        System.out.println("a 的年齡為 " + a.age + " 歲");

        PersonB b = new PersonB();
        //b.age = 900;
        b.setAge(1000);

        System.out.println("b 的年齡為 " + b.getAge() + " 歲");

        PersonC c = new PersonC();
        //c.age = 900;
        c.setAge(1000);

        System.out.println("c 的年齡為 " + c.getAge() + " 歲");
    }
}
```
