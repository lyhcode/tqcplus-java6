# if 和 if/else 敘述

簡單的 IF 敘述句。

    if (boolean_expression) {
        statement;
    }

IF-ELSE 敘述句。

    if (boolean_expression) {
        statement1;
    }
    else {
        statement2;
    }

IF-ELSE-ELSE IF 敘述句。

    if (boolean_expression1) {
        statement1;
    }
    else if (boolean_expression2) {
        statement2;
    }
    else {
        statement3;
    }

巢狀 IF 結構。

    if (boolean_expression1) {
        if (boolean_expression2) {
            statement1;
        }
        else {
            statement2;
        }
        statement3;
    }

範例（1）：分數判斷使用 IF-ELSE

    int score = 59;
    
    if (score >= 60) {
        System.out.println("及格");
    }
    else {
        System.out.println("不及格");
    }

範例（2）：分數判斷使用 IF-ELSE-IF-ELSE

（**錯誤**用法示範）

    int score = 85;
    
    if (score >= 60) {
        System.out.println("及格");
    }
    else if (score >= 80) {
        System.out.println("高分");
    }
    else {
        System.out.println("不及格");
    }

（正確用法）

    int score = 85;
    
    if (score >= 80) {
        System.out.println("高分");
    }
    else if (score >= 60) {
        System.out.println("及格");
    }
    else {
        System.out.println("不及格");
    }

＊需要注意判斷有執行先後次序

範例（3）：分數判斷使用巢狀 IF 結構

    if (score >= 60) {
        if (score >= 80) {
            System.out.println("高分");
        }
        else {
            System.out.println("及格");
        }
    }
    else {
        System.out.println("不及格");
    }

