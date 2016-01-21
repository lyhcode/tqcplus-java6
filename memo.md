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