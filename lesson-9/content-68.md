# 內涵式遞迴

階乘函數可以用 Java 寫成如下的程式碼，我們將之命名為 factorial。

       factorial(3)
    => return n * factorial(n - 1);             // n=3
    => return 3 * factorial(2);
    => return 3 * (n * factorial(n - 1));       // n=2
    => return 3 * (2 * factorial(1));
    => return 3 * (2 * (n * factorial(n - 1))); // n=1
    => return 3 * (2 * (1 * factorial(0)));
    => return 3 * (2 * (1 * 1));                // n=0
    => return 3 * (2 * (1 * 1));
    => 6

觀察以上的執行狀況，呼叫 factorial 的遞迴呼叫是內涵(embedded)在乘法算式 (n * ...) 之內。而程式的執行結果是在最後一個遞迴呼叫 factorial(0) 完成後才依序累乘 (3 * (2 * (1 * 1))) 而得的。這種類型的遞迴程序稱為內涵式遞迴（embedded recursion）。
