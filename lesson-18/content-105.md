# 題目二

1. 請設計一個LunchBox(便當)的類別，其資料屬性與方法要求如下:

2. 資料屬性:
   1. calorie: 型態為整數(int)，代表該便當的熱量。
   2. content: 代表便當所含的菜色，請使用Vector來儲存。

3. 方法:
   1. add: 傳入一個Food類別的物件並將之存放到content中。
   2. getCalorie:計算該便當所含菜色的總熱量。

參考右側的程式碼，完成題目要求以新增兩種不同的便當並計算其所含之熱量。

難

程式及輸出全部正確：10分

## 執行結果

```
Total calories of an economy lunch box are 2800.
Total calories of a valued-choice lunch box are 3360.
```

## 程式碼

JPA06_2.java

```java
import java.util.Vector;

abstract class Food
{
    private int amount;
    private int calorie;
    
    Food()
    {
    }
    
    Food(int grams)
    {
        amount = grams;
    }
    
    void setCaloriePerGram(int c)
    {
        calorie = c;
    }
    
    int getAmount()
    {
        return amount;
    }
    
    int getCalorie()
    {
        return amount*calorie;
    }
}

class Rice extends Food
{
    Rice(int grams)
    {
        super(grams);
        setCaloriePerGram(1);
    }
}

class Egg extends Food
{
    Egg(int grams)
    {
        super(grams);
        setCaloriePerGram(2);
    }
}

class Cabbage extends Food
{
    Cabbage(int grams)
    {
        super(grams);
        setCaloriePerGram(1);
    }
}

class PorkRib extends Food
{
    PorkRib(int grams)
    {
        super(grams);
        setCaloriePerGram(10);
    }
}

class Carrot extends Food
{
    Carrot(int grams)
    {
        super(grams);
        setCaloriePerGram(1);
    }
}

class LunchBox
{
    private int calorie;
    private Vector<Food> content;
    LunchBox()
    {
        content = new Vector<Food>();
    }
    
    void add(Food f)
    {
        content.add(f);
    }
    
    int getCalorie()
    {
        int total=0;
        for(Food f : content)
        {
            total+=f.getCalorie();
        }
        return total;
    }
}

class JPA06_2 {
    public static void main(String args[]) {
        LunchBox economy = new LunchBox();
        economy.add(new Rice(200));
        economy.add(new Cabbage(100));
        economy.add(new PorkRib(250));
        System.out.println("Total calories of an economy lunch box are " + economy.getCalorie() +".");
        
        LunchBox valuedChoice = new LunchBox();
        valuedChoice.add(new Rice(200));
        valuedChoice.add(new Egg(30));
        valuedChoice.add(new Carrot(100));
        valuedChoice.add(new PorkRib(300));
        System.out.println("Total calories of a valued-choice lunch box are " + valuedChoice.getCalorie()+".");
        
    }
}
```

## 開始練習

```java
...

class JPD06_2
{
    public static void main(String args[])
    {
        LunchBox economy = new LunchBox();
        economy.add(new Rice(200));
        economy.add(new Cabbage(100));
        economy.add(new PorkRib(250));
        System.out.println("Total calories of an economy lunch box are " + economy.getCalorie() +".");
        
        LunchBox valuedChoice = new LunchBox();
        valuedChoice.add(new Rice(200));
        valuedChoice.add(new Egg(30));
        valuedChoice.add(new Carrot(100));
        valuedChoice.add(new PorkRib(300));
        System.out.println("Total calories of a valued-choice lunch box are " + valuedChoice.getCalorie()+".");
        
    }
}
```
