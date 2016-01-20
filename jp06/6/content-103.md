# 題目五

續上題。

1. 撰寫一個能夠印出五位教師（不含行政主管Fang）的姓名及薪資(不扣稅及不扣健保費)的方法。這個方法利用例外處理將薪水少於1500的教師姓名前印出兩個**號。

中：程式及輸出全部正確使給分。

## 執行結果

```
Paul 3420.0
**Mary 1200.0
Eric 4830.0
Peter 3600.0
**John 800.0
```

## 程式碼

JPA06_5.java

```java
import java.util.HashMap;
import java.util.Map;

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
		} else {
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

class TeacherDB {

	Map<String, Teacher> map = new HashMap<String, Teacher>();

	public void store(String name, Teacher t) {
		map.put(name, t);
	}

	public double totalOfAll() {
		double result = 0;

		for (Teacher t : map.values()) {
			result += t.afterTaxIns();
		}

		return result;
	}

	public void printAllTeacher() {
		for (Teacher t : map.values()) {
			try {
				if (t.salary() < 1500) {
					throw new Exception();
				}
				System.out.println(t.name + " " + t.salary());
			} catch (Exception ex) {
				System.out.println("** " + t.name + " " + t.salary());
			}
		}
	}
}

public class JPD06_5 {
	public static void main(String argv[]) {
		PartTimeTeacher p1 = new PartTimeTeacher("John", 400, 2);
		PartTimeTeacher p2 = new PartTimeTeacher("Mary", 300, 4);
		FullTimeTeacher f1 = new FullTimeTeacher("Peter", 400, 9);
		FullTimeTeacher f2 = new FullTimeTeacher("Paul", 300, 12);
		FullTimeTeacher f3 = new FullTimeTeacher("Eric", 350, 15);

		TeacherDB school = new TeacherDB();
		school.store("John", p1);
		school.store("Mary", p2);
		school.store("Peter", f1);
		school.store("Paul", f2);
		school.store("Eric", f3);

		school.printAllTeacher();
	}
}
```

## 開始練習

```java
...

public class JPD06_5 {
    public static void main(String argv[]) {
        PartTimeTeacher p1 = new PartTimeTeacher("John",400,2);
        PartTimeTeacher p2 = new PartTimeTeacher("Mary",300,4);
        FullTimeTeacher f1 = new FullTimeTeacher("Peter",400,9);
        FullTimeTeacher f2 = new FullTimeTeacher("Paul",300,12);
        FullTimeTeacher f3 = new FullTimeTeacher("Eric",350,15);
        
        TeacherDB school = new TeacherDB();
        school.store("Paul", f2);
        school.store("Mary", p2);
        school.store("Eric", f3);
        school.store("Peter", f1);
        school.store("John", p1);
       
        school.printAllTeacher();
    }
}
```
