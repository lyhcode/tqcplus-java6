# 宣告陣列

陣列內的儲存值可以是：

1. primitive type；
2. 也可以是 reference type。

在本節中我們只會以 primitive type 的儲存值當作範例。

例如：

    {2.4, 3.9, 4.0, 1.3}

以上是一個長度是 4，索引是 0 - 3 而型態是 double 的陣列。這個陣列可以由以下的程式碼得到：

    // 宣告 aDoubleArray 是一個 double array
    double[] aDoubleArray;
    
    // 使用 new 挪出可以存放 4 個 double 的儲存區
    aDoubleArray = new double[4];
    
    aDoubleArray[0] = 2.4;
    aDoubleArray[1] = 3.9;
    aDoubleArray[2] = 4.0;
    aDoubleArray[3] = 1.3;

宣告 aDoubleArray 時可以賦予初始值：

    double[] aDoubleArray = new double[4];

也可以直接初始化陣列的內容：

    double[] aDoubleArray = {2.4, 3.9, 4.0, 1.3};

而以下的程式碼可以印出其值：

    for (int i = 0; i < aDoubleArray.length; i++)
        System.out.println(aDoubleArray[i]);

