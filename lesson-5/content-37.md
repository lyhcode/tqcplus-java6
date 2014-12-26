# switch 敘述

switch 的語法結構如下：

    switch (variable) {
        case literal_value1:
            statements;
            break;
        case literal_value2:
            statements;
            break;
        default:
            statements;
    }

範例（1）：顯示水果名稱

    int a = 1;
    
    switch (a) {
        case 1:
            System.out.println("Apple");
        break;
        case 2:
            System.out.println("Banana");
        break;
        default:
            System.out.println("Pineapple");
    }
