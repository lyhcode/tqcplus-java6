# 確認已安裝的 Java 版本

打開命令提示字元視窗「開始 > 附屬應用程式 > 命令提示字元」

- 輸入 **java -version** 後按ENTER
- 輸入 **javac -version** 後按ENTER
- 查看輸出訊息是否包含正確版本資訊。

**java -version** 指令正確的輸出畫面範例


    java version "1.6.0_27"
    Java(TM) SE Runtime Environment (build 1.6.0_27-b07)
    Java HotSpot(TM) Client VM (build 17.0-b17, mixed mode, sharing)

**javac -version** 指令正確的輸出畫面範例

    javac 1.6.0_27

請注意：版本必須是 1.6 以上！

若版本顯示不正確（例如出現 1.5.0 或更早版本），表示您的 PATH 設定中包含舊版 JDK 的路徑，請移除舊的路徑，並將新路徑置於設定的開頭。未安裝 JDK，或安裝 JDK 後未正確設定 PATH，會出現以下錯誤訊息。

    'javac' 不是內部或外部命令、可執行的程式或批次檔。

或是

    'java' 不是內部或外部命令、可執行的程式或批次檔。

### 如果以上皆正確 ###

恭喜！您的 Java 開發環境已正確安裝，可以開始寫程式了！

提醒：您必須**關閉所有瀏覽器視窗及相關程式**後，再重新開啟網頁，系統的設定才能發揮作用。

