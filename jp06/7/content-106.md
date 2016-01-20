# 題目三

(1) 為各項菜色增加unitCost(單位成本)屬性，
    其型態為整數(int)，代表每公克之成本。

(2) 為各項菜色增加getCost方法，以取得該菜色
    的成本(意即 unitCost*amount)。

(3) 為便當增加priceRatio變數，表示該便當的
    售價為所含菜色的cost總和乘上其priceRatio。

(4) 為便當增加一個getPrice方法，以取得該便當
    的售價(此方法的傳回值型態為double)。

各菜色的成本如下:

<table class="table">
<th>菜色名稱</th><th>每公克成本</th><tr>
<td>Rice</td><td>1</td><tr>
<td>Egg</td><td>2</td><tr>
<td>Cabbage</td><td>3</td><tr>
<td>ProkRib</td><td>8</td><tr>
<td>Carrot</td><td>3</td><tr>
</table>

參考右側程式碼，完成兩種便當的設計並印出所具備的熱量與售價。

難

程式及輸出全部正確：10分

輸出正確，但有重複的程式碼：5分

## 執行結果

```
Total calories of an economy lunch box are 2800
The price of an economy lunch box is 3000.0
Total calories of a valued-choice lunch box are 3360
The price of a valued-choice lunch box is 3848.0
```

## 程式碼

JPA06_3.java

```java
import java.util.Vector;

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
}

class JPA06_3
{
    public static void main(String args[])
    {
        LunchBox economy = new LunchBox();
        economy.add(new Rice(200));
        economy.add(new Cabbage(100));
        economy.add(new PorkRib(250));
        economy.setPriceRatio(1.2);
        System.out.println("Total calories of an economy lunch box are " + economy.getCalorie());
        System.out.println("The price of an economy lunch box is " + economy.getPrice());
        
        LunchBox valuedChoice = new LunchBox();
        valuedChoice.add(new Rice(200));
        valuedChoice.add(new Egg(30));
        valuedChoice.add(new Carrot(100));
        valuedChoice.add(new PorkRib(300));
        valuedChoice.setPriceRatio(1.3);
        System.out.println("Total calories of a valued-choice lunch box are " + valuedChoice.getCalorie());
        System.out.println("The price of a valued-choice lunch box is " + valuedChoice.getPrice());        
    }
}
```

## 開始練習

```java
...

class JPD06_3 {
    public static void main(String args[]) {
        LunchBox economy = new LunchBox();
        economy.add(new Rice(200));
        economy.add(new Cabbage(100));
        economy.add(new PorkRib(250));
        economy.setPriceRatio(1.2);
        System.out.println("Total calories of an economy lunch box are " + economy.getCalorie());
        System.out.println("The price of an economy lunch box is " + economy.getPrice());
        
        LunchBox valuedChoice = new LunchBox();
        valuedChoice.add(new Rice(200));
        valuedChoice.add(new Egg(30));
        valuedChoice.add(new Carrot(100));
        valuedChoice.add(new PorkRib(300));
        valuedChoice.setPriceRatio(1.3);
        System.out.println("Total calories of a valued-choice lunch box are " + valuedChoice.getCalorie());
        System.out.println("The price of a valued-choice lunch box is " + valuedChoice.getPrice());        
    }
}
```
