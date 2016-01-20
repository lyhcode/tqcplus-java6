# memo

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

```
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