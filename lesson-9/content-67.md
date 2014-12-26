# 累計答案值的遞迴程序

我們練習了幾個傳回 true 或 false 的程序。這些題目的答案不需要經過累計，例如：累加、累乘、或累積成字串的過程。這個單元我們將練習需要經過累計才能計算出答案的遞迴程序。

假設我們需要撰寫一個能夠計算一個 string 中有幾個 true 的程序。我們將這個程序命名為 countTrue，測試案例如下：

    countTrue("");     => 0
    countTrue("1101"); => 3

很顯然的，在程序執行的過程中如果遇到 1（true） 則需要將 1 加入結果之中。

我們可以追蹤這個程式是怎麼執行的：

       countTrue("");
    => 0

"" 使 str.equals("") 成立因此傳回0

       countTrue("1");
    => (1 + countTrue("");)
    => (1 + 0)
    => 1

"1" 使 (Integer.parseInt(str.substring(0, 1)) == 1) 成立因此傳回1

       countTrue("01");
    => countTrue("1");
    => 1

"01" 使 else 成立因此傳回1

       countTrue("101");
    => (1 + countTrue("01");
    => (1 + 1)
    => 2

"101" 使 (Integer.parseInt(str.substring(0, 1)) == 1) 成立因此傳回2

接下來，我們可以追蹤將一個有四個資料值的 string 傳入 countTrue 的執行狀況：

       countTrue("1101");
    => (1 + countTrue("101");)
    => (1 + (1 + countTrue("01");))
    => (1 + (1 + countTrue("1");))
    => (1 + (1 + (1 + countTrue("");)))
    => (1 + (1 + (1 + 0)))
    => 3

另外，countTrue 的型態是： String -> int 。
