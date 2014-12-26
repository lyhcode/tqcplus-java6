# 三元運算子

簡單的 IF-ELSE 敘述句。

    if (boolean_expression) {
        variable1 = result1;
    }
    else {
        variable1 = result2;
    }

可以利用三元運算子改寫成：

    variable1 = boolean_expression?result1:result2;

範例（1）：分數判斷

    int score = 85;
    
    System.out.println( score>=60 ? "及格" : "不及格" );
    
    System.out.println(
        score>=60 ? (score>=80 ? "高分" : "及格") : "不及格"
    );
