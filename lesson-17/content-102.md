# 題目四

續上題。

1. 請使用 HashMap 撰寫一個能夠存放教師資料的類別，HashMap的key值為老師名稱(String)，value值為該老師物件。
2. 將這些教師物件存入一個由這個類別所製造的實例中，然後撰寫一個totalOfAll方法，將所有老師個別的稅後薪資(afterTaxIns)相加，輸出總和。

中：程式及輸出全部正確使給分。

## 執行結果

```
Total salary: 18345.0
```

## 程式碼

JPA06_4.java

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

}

public class JPA06_4 {
    public static void main(String argv[]) {
        PartTimeTeacher p1 = new PartTimeTeacher("John",400,2);
        PartTimeTeacher p2 = new PartTimeTeacher("Mary",300,4);
        FullTimeTeacher f1 = new FullTimeTeacher("Peter",400,9);
        FullTimeTeacher f2 = new FullTimeTeacher("Paul",300,12);
        FullTimeTeacher f3 = new FullTimeTeacher("Eric",350,15);
        Manager am1 = new Manager("Fang", 500, 12, 3);
                
        TeacherDB school = new TeacherDB();
        school.store("John", p1);
        school.store("Mary", p2);
        school.store("Peter", f1);
        school.store("Paul", f2);
        school.store("Eric", f3);
        school.store("Fang", am1);
        System.out.println("Total salary: " + school.totalOfAll());
    }
}
```

## 開始練習

```java
...

public class JPD06_4 {
    public static void main(String argv[]) {
        PartTimeTeacher p1 = new PartTimeTeacher("John",400,2);
        PartTimeTeacher p2 = new PartTimeTeacher("Mary",300,4);
        FullTimeTeacher f1 = new FullTimeTeacher("Peter",400,9);
        FullTimeTeacher f2 = new FullTimeTeacher("Paul",300,12);
        FullTimeTeacher f3 = new FullTimeTeacher("Eric",350,15);
        Manager am1 = new Manager("Fang", 500, 12, 3);
    
        TeacherDB school = new TeacherDB();
        school.store("John", p1);
        school.store("Mary", p2);
        school.store("Peter", f1);
        school.store("Paul", f2);
        school.store("Eric", f3);
        school.store("Fang", am1);
        System.out.println("Total salary: " + school.totalOfAll());
    }
}
```
