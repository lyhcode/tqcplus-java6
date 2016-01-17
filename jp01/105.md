# 105. 存錢筒

### 題目說明 ###

請參考 JPD01 程式碼，將 class JPD01 修改為 class JPA01，依下列題意完成作答。

### 設計說明 ###

1. 有一位小朋友從小就開始把1元、5元、10元、50元的零用錢，投進自己的存錢筒裡。請計算出存錢筒中金錢的總額。
2. 程式執行時，首先要求輸入姓名，顯示【請輸入您的姓名：】，顯示如 Screen Dump。
3. 姓名輸入完畢，要求輸入銅板個數，顯示如 Screen Dump。
4. 依序要求輸入1元、5元、10元、50元硬幣的數量，待數入完才可再顯示下一列，顯示如 Screen Dump。
5. 金額輸入完畢，輸出總額，執行結果顯示如 Screen Dump。

## 執行結果

```
請輸入小孩姓名：林小佳
Hi, 林小佳,請輸入你的銅板的個數：
請輸入1元的數量：80
請輸入5元的數量：70
請輸入10元的數量：55
請輸入50元的數量：38
您的錢總共有：2 千  8 百  8 十  0 元
```

## 程式碼

JPA01.java

```java
import java.util.Scanner;
public class JPA01 {
    public static void main(String[] args) {
        String name;
  	    int oned, fived, tend, fifd;      	
	    int totalm;
	    int totalhun;
	    int totalten;
	    int totalunit;
	    int totalt;
	     
        Scanner keyboard = new Scanner(System.in);
        System.out.print("請輸入小孩姓名：");
        name = keyboard.next();
        System.out.printf("Hi, %s,請輸入你的銅板的個數：\n",name);
        System.out.print("請輸入1元的數量：");
        oned = keyboard.nextInt();
        System.out.print("請輸入5元的數量：");
        fived = keyboard.nextInt();
        System.out.print("請輸入10元的數量：");
        tend = keyboard.nextInt();
        System.out.print("請輸入50元的數量：");
        fifd = keyboard.nextInt();
        totalm = oned + 5 * fived + 10 * tend + 50 * fifd;
        totalt = totalm / 1000; 
        totalm = totalm % 1000;
        totalhun = totalm / 100; 
        totalm = totalm % 100;
        totalten = totalm / 10; 
        totalunit = totalm % 10;
        System.out.printf("您的錢總共有：%d 千  %d 百  %d 十  %d 元\n", totalt, 
totalhun, totalten, totalunit);
    }
}

```

## 開始練習

```java
import java.util.Scanner;
public class JPD01 {
    public static void main(String[] args) {
        String name;
  	    int oned, fived, tend, fifd;      	
	    int totalm;
	    int totalhun;
	    int totalten;
	    int totalunit;
	    int totalt;
	     
        Scanner keyboard = new Scanner(System.in);
        System.out.print("請輸入小孩姓名：");
        name = keyboard.next();
        System.out.printf("Hi, %s,請輸入你的銅板的個數：\n",name);
        System.out.print("請輸入1元的數量：");
        oned = keyboard.nextInt();
        System.out.print("請輸入5元的數量：");
        fived = keyboard.nextInt();
        System.out.print("請輸入10元的數量：");
        tend = keyboard.nextInt();
        System.out.print("請輸入50元的數量：");
        fifd = keyboard.nextInt();
        totalm = ____________________________________;
        totalt = _____________; 
        totalm = _____________;
        totalhun = ___________; 
        totalm = ____________;
        totalten = ___________; 
        totalunit = ___________;
        System.out.printf("您的錢總共有：%d 千  %d 百  %d 十  %d 元\n", totalt, 
totalhun, totalten, totalunit);
    }
}```
