# 關於中文編碼問題

下載並編譯 ChineseMain.java 程式：

    javac ChineseMain.java

你會發現編譯器產生錯誤訊息：

    ChineseMain.java:3: error: unmappable character for encoding MS950
            System.out.println("?銝剜?");
                            ^
    ChineseMain.java:3: error: unmappable character for encoding MS950
            System.out.println("?銝剜?");
                                 ^
    2 errors

並非這個程式的寫法有問題，而是「中文編碼」需要加上額外的指令。錯誤訊息中提示的「MS950」是 Windows 系統的預設中文編碼，但一般我們會習慣用 UTF-8（一種較廣泛採用的 Unicode ）編碼格式，所以需要指定編碼格式設定。重新使用以下的指令再次編譯：

    javac -encoding UTF-8 ChineseMain.java

再執行即可看到「我是中文」的輸出結果：

    java ChineseMain

