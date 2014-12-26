# 繼承

請思考 Person、Student 及 Teacher 的繼承關係。

![ClassDiagram][1]

  [1]: http://yuml.me/21faca3a

上面的 UML 圖表示 Person 為父類別，Student 與 Teacher 分別繼承 Person，這兩個類別稱為子類別。

## 執行結果

```
true
true
John
Jack
```

## 程式碼

Main.java

```java
class Person {
    String name;
    
    public void setName(String name) {
    	this.name = name;
    }
    
    public String getName() {
    	return name;
    }
}

class Teacher extends Person {
}

class Student extends Person {
}

public class Main {
    public static void main(String[] args) {
        Person teacher = new Teacher();
        teacher.setName("John");
        
        Person student = new Student();
        student.setName("Jack");
        
        System.out.println(teacher instanceof Person);
        System.out.println(student instanceof Person);
        
        System.out.println(teacher.getName());
        System.out.println(student.getName());
    }
}

```

## 開始練習

```java
class Person {
    String name;
    
    public void setName(String name) {
    	this.name = name;
    }
    
    public String getName() {
    	return name;
    }
}

class Teacher extends Person {
}

class Student extends Person {
}

public class Main {
    public static void main(String[] args) {
        Person teacher = new Teacher();
        teacher.setName("John");
        
        Person student = new Student();
        student.setName("Jack");
        
        System.out.println(_______ instanceof Person);
        System.out.println(_______ instanceof Person);
        
        System.out.println(teacher._________);
        System.out.println(student._________);
    }
}
```
