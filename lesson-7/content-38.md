# while 迴圈

while 迴圈的語法：

    while (boolean_expression) {
        statements;
    }

boolean_expression 邏輯運算產生 true 或 false，每次執行迴圈內容前都會先判斷此運算結果。

while 迴圈又稱為「前測試迴圈」，因為在進入迴圈前，就會先執行一次運算式的判斷。

如果第一次判斷運算式的結果就不成立，則迴圈內容連一次也不會被執行。

    int input = 100;
    
    while (input > 100) {
        System.out.println("迴圈內容被執行");
    }


如果判斷運算式結果恆為 true，則迴圈內容就會不斷執行（變成無窮迴圈）。以下程式碼僅供參考，請不要執行以免造成無窮迴圈（可能導致程式停止回應）。

    int input = 500;
    
    while (input > 100) {
        System.out.println("迴圈內容被執行");
    }

合理的迴圈設計，應該要有起始與終止的條件。例如：

    int input = 100;
    
    while (input <= 500) {
        System.out.println("input = " + input);
        input += 100;
    }
    
這段程式碼因為 input 的值 100 小於 500，所以第一次迴圈的運算式判斷結果成立，開始執行迴圈內容，在印出 input 的內容後，input 會先累加 100 之後，再進行第二次運算式判斷。直到第六次判斷 input 已經大於 500，迴圈此時才終止。
