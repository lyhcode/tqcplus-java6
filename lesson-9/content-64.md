# 費式數列

十三世紀的義大利數學家費伯那奇 (Fibonacci)提出了一個有趣的問題：假定一對兔子出生滿兩個月就可以生一對小兔子，之後每一個月又可以再生一對小兔子。假定現在有一對剛生下來的小兔子，請問一年以後應該有幾對兔子？

年初，只有1對小兔子。 

一月，小兔子還沒長大，所以還是只有1+0=1對。 

二月，小兔子長成大兔子，開始生下一對小兔子，共有1+1＝2對。 

三月，大兔子又生了一對小兔子，而小兔子還沒長大，所以共有2+1=3對。 

四月，第一對小兔子也長大開始生小兔子，這個月生了兩對，總共有3+2=5對。 

五月，第二對小兔子也長大了，所以有三對大兔子會生小兔子，總共有5+3＝8對。 

六月，第四月生的小兔子也長大了，所以這個月生了5對，總共有8+5＝13對。 

... 


你有沒有發現，每個月的小兔子總數就是前一個月加上前前一個月的兔子數目？繼續加下去，你能算到多少？ 

「費氏數列」是一組規則得令人感到神奇的數列。如果把費氏數列的任一項除以其前一項，將會越來越接近一個數字：1.618…，這個數字被稱為「黃金比例」。

## 執行結果

```
n=5
n=4
n=3
n=2
n=1
n=0
f(0)=1
f(1)=1
f(2)=2
f(3)=6
f(4)=24
f(5)=120
```

## 程式碼

Fibonacci.java

```java
class Fibonacci {
    public static void main(String[] args) {
        int x = f(5);
        System.out.println("f(5)="+x);
    }
 
    public static int f(int n) {
        System.out.println("n="+n);
        if (n == 0)
            return 1;
        else {
            int fn_1 = f(n-1);
            System.out.println("f("+(n-1)+")="+fn_1);
            return fn_1*n;
        }
    }
}
```

## 開始練習

```java
class Fibonacci {
    public static void main(String[] args) {
        int x = f(5);
        System.out.println("f(5)="+x);
    }
 
    public static int f(int n) {
        // 請完成程式碼
    }
}```
