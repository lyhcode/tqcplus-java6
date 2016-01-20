# 題目三

續上題。

1. 請寫一個比較兩位教師，那一位薪水較高的方法。
2. 比較 Fang 與 Eric 哪一位薪水(未扣除健保費與稅金前的薪水)較高？
3. 比較 Eric 與 John 哪一位薪水(未扣除健保費與稅金前的薪水)較高？

中

程式及輸出全部正確：10分

輸出正確，但有重複的程式碼：5分

## 執行結果

```
Fang is higher than Eric
Eric is higher than John
```

## 程式碼

JPA06_3.java

```java
abstract class Teacher {
	protected String name;
	protected int rate;
	protected int totalHours;
	
	abstract public double salary();

	public double afterTaxIns() {
		return salary() * 0.9 - 100;
	}
	
	public void compare(Teacher t) {
		if (this.salary() > t.salary()) {
			System.out.println(this.name + " is higher than " + t.name);
		}
		else {
			System.out.println(t.name + " is higher than " + this.name);
		}
	}
}

class PartTimeTeacher extends Teacher {

	public PartTimeTeacher(String name, int rate, int totalHours) {
		this.name = name;
		this.rate = rate;
		this.totalHours = totalHours;
	}

	public double salary() {
		return totalHours * rate;
	}
}

class FullTimeTeacher extends Teacher {
	
	public FullTimeTeacher(String name, int rate, int totalHours) {
		this.name = name;
		this.rate = rate;
		this.totalHours = totalHours;
	}

	public double salary() {
		return 9 * rate + ((totalHours - 9) * rate * 0.8);
	}
}

class Manager extends FullTimeTeacher {

	private int rank;

	public Manager(String name, int rate, int totalHours, int rank) {
		super(name, rate, totalHours);
		
		this.rank = rank;
	}
	
	public double salary() {
		return super.salary() + rank * 500;
	}

	public double getTotalSalary() {
		return salary();
	}
}


public class JPA06_3 {
    public static void main(String argv[]) {
        PartTimeTeacher p1 = new PartTimeTeacher("John",400,2);
        PartTimeTeacher p2 = new PartTimeTeacher("Mary",300,4);
        FullTimeTeacher f1 = new FullTimeTeacher("Peter",400,9);
        FullTimeTeacher f2 = new FullTimeTeacher("Paul",300,12);
        FullTimeTeacher f3 = new FullTimeTeacher("Eric",350,15);
        
        Manager am1 = new Manager("Fang", 500, 12, 3);
       
        am1.compare(f3);
        p1.compare(f3);
    }
}
```

## 開始練習

```java
...

public class JPD06_3 {
    public static void main(String argv[]) {
        PartTimeTeacher p1 = new PartTimeTeacher("John",400,2);
        PartTimeTeacher p2 = new PartTimeTeacher("Mary",300,4);
        FullTimeTeacher f1 = new FullTimeTeacher("Peter",400,9);
        FullTimeTeacher f2 = new FullTimeTeacher("Paul",300,12);
        FullTimeTeacher f3 = new FullTimeTeacher("Eric",350,15);
        Manager am1 = new Manager("Fang", 500, 12, 3);

        am1.compare(f3);
        p1.compare(f3);
    }
}
```
