# 題目四

1. 請修改LunchBox類別，提供比較兩個便當何者較便宜的方法，其名稱為isCheaperThan。
2. 參考右側程式碼，完成題目要求。

中

程式及輸出全部正確：10分

## 執行結果

```
Is the economy lunch box cheaper than the valued-choice? YES!
```

## 程式碼

JPA06_4.java

```java
import java.util.Vector;
import java.util.ArrayList;

abstract class Food
{
    private int amount;
    private int calorie;
    private int unitCost;
    
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
    
    void setUnitCost(int c)
    {
        unitCost = c;
    }
    
    int getCost()
    {
        return amount*unitCost;
    }
}

class Rice extends Food
{
    Rice(int grams)
    {
        super(grams);
        setCaloriePerGram(1);
        setUnitCost(1);
    }
}

class Egg extends Food
{
    Egg(int grams)
    {
        super(grams);
        setCaloriePerGram(2);
        setUnitCost(2);
    }
}

class Cabbage extends Food
{
    Cabbage(int grams)
    {
        super(grams);
        setCaloriePerGram(1);
        setUnitCost(3);
    }
}

class PorkRib extends Food
{
    PorkRib(int grams)
    {
        super(grams);
        setCaloriePerGram(10);
        setUnitCost(8);
    }
}

class Carrot extends Food
{
    Carrot(int grams)
    {
        super(grams);
        setCaloriePerGram(1);
        setUnitCost(3);
    }
}

class LunchBox
{
    private int calorie;
    private Vector<Food> content;
    private double priceRatio;
    
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
    
    void setPriceRatio(double ratio)
    {
        priceRatio = ratio;
    }
    
    double getPrice()
    {
        int totalCost=0;
        for(Food f : content)
        {
            totalCost+=f.getCost();
        }
        return totalCost * priceRatio;
    }
    
    Vector getContent()
    {
        return content;
    }
    
    String isCheaperThan(LunchBox lb)
    {
        if(this.getPrice() < lb.getPrice())
        {
            return "YES!";
        }
        else
        {
            return "NO!";
        }
    }
}

class JPA06_4 {
    public static void main(String args[]) {
        LunchBox economy = new LunchBox();
        economy.add(new Rice(200));
        economy.add(new Cabbage(100));
        economy.add(new PorkRib(250));
        economy.setPriceRatio(1.2);
        
        LunchBox valuedChoice = new LunchBox();
        valuedChoice.add(new Rice(200));
        valuedChoice.add(new Egg(30));
        valuedChoice.add(new Carrot(100));
        valuedChoice.add(new PorkRib(300));
        valuedChoice.setPriceRatio(1.3);

        System.out.println("Is the economy lunch box cheaper than the valued-choice? " + economy.isCheaperThan(valuedChoice));
        
    }
}
```

## 開始練習

```java
...

class JPD06_4 {
    public static void main(String args[]) {
        LunchBox economy = new LunchBox();
        economy.add(new Rice(200));
        economy.add(new Cabbage(100));
        economy.add(new PorkRib(250));
        economy.setPriceRatio(1.2);
        
        LunchBox valuedChoice = new LunchBox();
        valuedChoice.add(new Rice(200));
        valuedChoice.add(new Egg(30));
        valuedChoice.add(new Carrot(100));
        valuedChoice.add(new PorkRib(300));
        valuedChoice.setPriceRatio(1.3);

        System.out.println("Is the economy lunch box cheapter than the valued-choice? " + economy.isCheapterThan(valuedChoice));
        
    }
}
```
