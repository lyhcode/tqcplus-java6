# 安裝 Java 開發工具

* 本文所稱之 JDK，係指 Oracle 公司之「Java Platform, Standard Edition」軟體。
* 建議搭配的 JDK **6(1.6)** 或 **7** 版本，建議您取得最新發行的穩定版本。

### 安裝 JDK 於 Windows 作業系統 ###

#### 下載JDK6 ####

您可以在以下的網站找到 JDK 檔案下載。

* Oracle [Java SE Downloads][1]
* 備份位址 [jdk-6u27-windows-i586.exe][2]

以 32 位元 Windows 作業系統為例，JDK 6 Update 27 的安裝檔案名稱為：

    jdk-6u27-windows-i586.exe

### 設定PATH與CLASSPATH ###

首先開啟系統變數的設定視窗，依照Windows作業系統版本的不同，其操作方式請參考以下說明。

#### Windows XP ####

  * 桌面 > 我的電腦(圖示上按滑鼠右鍵) > 內容(點擊) > 進階(選取) > 環境變數(點擊)

#### Windows 7 ####

  * 桌面 > 我的電腦(圖示上按滑鼠右鍵) > 內容(點擊) > 進階系統設定(點擊) > 進階(選取) > 環境變數(點擊)

在「**系統變數**」區進行以下操作：

**修改PATH**

找到 PATH 按「編輯」按鈕，在原設定**最前方**加入以下路徑(須先確認路徑是否存在，分號是路徑之間的分隔符號，一定要加)。

    C:\Program Files\Java\jdk1.6.0_27\bin;

註：**1.6.0_27**視安裝版本而定，請使用檔案瀏覽器打開 Java 安裝路徑（通常為C:\Program Files\Java），檢視已安裝的版本名稱。

**設定CLASSPATH**

同樣在「系統變數」區域，找到CLASSPATH按「編輯」按鈕或「新增」按鈕(若CLASSPATH不存在請用新增)，在原設定最前方加入以下路徑(須先確認路徑是否存在，分號"**;**"是路徑之間的分隔符號，一定要加)。

    .;C:\Program Files\Java\jdk1.6.0_27\lib

註：**1.6.0_27**視安裝版本而定。

  [1]: http://www.oracle.com/technetwork/java/javase/downloads/index.html
  [2]: http://share.plweb.org/jdk-6u27-windows-i586.exe
