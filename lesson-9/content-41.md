# 簡易的遞迴程式

allTrue(“111”) ; 的執行過程可 trace 如下：

       allTrue("111")
    => allTrue("11")
    => allTrue("1")
    => allTrue("")
    => true

allTrue(“1101”) ; 的執行過程可 trace 如下：

       allTrue("1101")
    => allTrue("101")
    => allTrue("01")
    => false

觀察 allTrue 這個程序以及它的執行過程，我們發現：

1. allTrue 內有三個執行的可能（if 條件判斷的三個條件情況）。
2. 其中一行呼叫 allTrue 自己。這個呼叫自己的遞迴呼叫，傳入少了頭一筆資料值的 String(str.substring(1))。另外兩行沒有遞迴呼叫，而程式執行到這兩行之後便傳回 true 或 false，然後結束。
3. if 條件判斷式，控制程式執行哪個式子。
4. allTrue 這個程式的輸出入型態是：String -> boolean，也就是傳入一個 String、傳出一個布林值的意思。

一般而言，遞迴程式都有類似的模式：

1. 有終止條件（termination condition）如：str.equals(“”)、n == 0。
2. 有遞迴呼叫，而遞迴呼叫所傳入的資料一定會趨近終止條件（例如使用 substring(1) 使 string 愈來愈縮短）。
