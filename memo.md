# 教學筆記

迴圈練習：九九乘法表（for-loop）

```java
for (int i = 1; i <= 9; i++) {
	
	for (int j = 1; j <= 9; j++) {
	
		System.out.printf("%d*%d=%d\t", i, j, i * j);
		
	}
	
	System.out.println();
}
```

迴圈練習：九九乘法表（while-loop）

```java
int i = 1;

while (i <= 9) {
	int j = 1;
	
	while (j <= 9) {
		System.out.printf("%d*%d=%d\t", i, j, i * j);
		
		j++;
	}
	
	System.out.println();
	
	i++;
}

```

列印倒三角形

```java
for (int x = 0; x < 5; x++) {
				
	for (int y = 0; y < x; y++) {
		System.out.print(" ");				
	}
	
	for (int y = 0; y < (9 - x * 2); y++) {
		System.out.print("*");
	}
	
	System.out.println();
}
```

Output

```
*********
 *******
  *****
   ***
    *
```

列印沙漏

```
for (int x = -4; x < 5; x++) {

	int n = 4 - Math.abs(x);
	
	for (int y = 0; y < n; y++) {
		System.out.print(" ");				
	}
	
	for (int y = 0; y < (9 - n * 2); y++) {
		System.out.print("*");
	}
	
	System.out.println();
}
```

Output

```
*********
 *******
  *****
   ***
    *
   ***
  *****
 *******
*********
```

for 迴圈與標籤

```java
outer:
for (int i = 0; i < 5; i++) {

	inner:
	for (int j = 0; j < 5; j++) {
		
		System.out.printf("i = %d, j = %d\n", i, j);
		
		continue;
	}
	
	System.out.println("outer");
}
```

迴圈轉遞迴練習

```java
public static void countDown(int n) {
	while (n >= 0) {
		System.out.println( n-- );
	}
	System.out.println("END");
}

public static void countDownR(int n) {
	if (n >= 0) {
		System.out.println(n);
		countDownR(n - 1);
	}
	else {
    	System.out.println("END");
	}
}
```

列印星號

```java
public static String star(int n) {
	if (n > 0) {
		return "*" + star(n - 1);
	}
	return "";
}
```


```java
    public static String star(int n) {
    	return n > 0 ? "*" + star(n - 1) : "";
    }
```

撲克牌遊戲

```
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class Main {

	private static Scanner scanner = new Scanner(System.in);
	
	public static void main(String[] args) {

		String[] poker = {
				"A", "2", "3", "4", "5", "6",
				"7", "8", "9", "10", "J", "Q", "K" };

		for (int i = 0; i < 13; i++) {
			int rnd = (int) (Math.random() * 13);

			String tmp = poker[i];
			poker[i] = poker[rnd];
			poker[rnd] = tmp;
		}
		
		List<String> computer = new ArrayList<String>();
		List<String> player = new ArrayList<String>();
		
		String input;
		int count = 0;
		
		do {
			// 電腦抽出一張牌
			computer.add(poker[count++]);
			
			// 玩家抽出一張牌
			player.add(poker[count++]);
			
			System.out.print("玩家：");
			print(player);
			
			if (total(player) >= 21) {
				break;
			}
			
			System.out.println("是否繼續抽牌(y/n)？");
			input = scanner.next();
		}
		while (input.equals("y"));
		
		System.out.print("玩家：");
		print(player);
		System.out.printf("點數：%d\n", total(player));
		
		System.out.print("電腦：");
		print(computer);
		System.out.printf("點數：%d\n", total(computer));


		if (total(player) == 21) {
			System.out.println("玩家勝！");
		}
		else if (total(player) > 21) {
			System.out.println("玩家爆牌！電腦勝！");
		}
		else if (total(computer) > 21) {
			System.out.println("電腦爆牌！玩家勝！");
		}
		else if (total(player) == total(computer)) {
			System.out.println("平手！");
		}
		else if (total(player) > total(computer)) {
			System.out.println("玩家勝！");
		}
		else {
			System.out.println("電腦勝！");
		}
		
	}

	private static void print(List<String> list) {
		for (String item : list) {
			System.out.printf("%s ", item);
		}
		System.out.println();
	}
	
	private static int total(List<String> list) {
		int total = 0;
		for (String item : list) {
			if (item.equals("A")) {
				total ++;
			}
			else if (item.equals("J") || item.equals("Q") || item.equals("K")) {
				total += 10;
			} else {
				total += new Integer(item);
			}
		}
		return total;
	}
}
```

費氏數列遞迴版

```
public static int fib(int n) {
	return n <= 1 ? n : fib(n - 1) + fib(n - 2);
}
```