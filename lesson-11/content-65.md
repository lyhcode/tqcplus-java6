# 多維陣列

多維陣列是一個陣列的元素本身也是陣列。例如以下這個二維陣列：

    String[][] names = {{"Boy", "Girl", "Man"},
                        {"Woman", "Father", "Son"}};
    for (int i = 0; i < 2; i++)
        for (int j = 0; j < 3; j++)
            System.out.printf(names[i][j]);

執行結果

    Boy
    Girl
    Man
    Woman
    Father
    Son
