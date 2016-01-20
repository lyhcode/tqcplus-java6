# 題目五

請設計一個SaleReport(銷售紀錄)類別，以儲存便當的銷售紀錄。相關要求如下:

1. 利用ArrayList以儲存所銷售的便當。每銷售一個便當，便呼叫add方法將所銷售的便當物件加以存放。
2. 設計一個可計算總銷售便當個數的方法，其名稱為getNumberOfLunchBox。
3. 設計一個可計算銷售便當的利潤(售價-成本)的方法，其名稱為getProfit。

參考右側程式碼，完成題目要求。

中

程式及輸出全部正確：10分

## 執行結果

```
2 lunch boxes have been sold.
Profit is 1388.
```

## 程式碼

JPA06_5.java

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
    
    Vector<Food> getContent()
    {
        return content;
    }
    
    String isCheapterThan(LunchBox lb)
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

class SaleReport
{
    private ArrayList<LunchBox> list = new ArrayList<LunchBox>();
    
    void add(LunchBox lb)
    {
        list.add(lb);
    }
    
    int getNumberOfLunchBox()
    {
        return list.size();
    }
    
    int getProfit()
    {
        int profit=0;
        for(LunchBox lb : list)
        {
            int totalCost=0;
            Vector<Food> content = lb.getContent();
            for(Food f : content)
            {
                totalCost+=f.getCost();
            }
            profit += (lb.getPrice()-totalCost);
        }
        return profit;        
    }
}

class JPA06_5 {
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
        
        SaleReport sr = new SaleReport();
        sr.add(economy);
        sr.add(valuedChoice);
        System.out.println( sr.getNumberOfLunchBox() + " lunch boxes have been sold.");
        System.out.println("Profit is " + sr.getProfit() + ".");
        
    }
}
```

## 開始練習

```java
...

class JPD06_5 {
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
        
        SaleReport sr = new SaleReport();
        sr.add(economy);
        sr.add(valuedChoice);
        System.out.println( sr.getNumberOfLunchBox() + " lunch boxes have been sold.");
        System.out.println("Profit is " + sr.getProfit() + ".");
        
    }
}
```
