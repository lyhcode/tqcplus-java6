# 抽象類別（abstract class）

    abstract class Animal {
        abstract public void eat(String food);
    }
    
    class Cat extends Animal {
        public void eat(String food) {
            //...
        }
    }
    
    class Dog extends Animal {
        public void eat(String food) {
            //...
        }
    }

請完成以下程式。

## 執行結果

```
個人電腦正在開機
筆記型電腦正在開機

```

## 程式碼

Main.java

```java
abstract class Computer {
    abstract public void boot();
}

class PC extends Computer {
    public void boot() {
        System.out.println("個人電腦正在開機");
    }
}

class NB extends Computer {
    public void boot() {
        System.out.println("筆記型電腦正在開機");
    }
}

public class Main {
    public static void main(String[] args) {
        Computer pc1 = new PC();
        Computer nb1 = new NB();
        
        pc1.boot();
        nb1.boot();
    }
}

```

## 開始練習

```java
abstract class Computer {
    abstract public void boot();
}

class PC extends Computer {
    //...
}

class NB extends Computer {
    //...
}

public class Main {
    public static void main(String[] args) {
        Computer pc1 = new PC();
        Computer nb1 = new NB();
        
        pc1.boot();
        nb1.boot();
    }
}
```
