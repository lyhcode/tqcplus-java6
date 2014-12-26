# 題目一

1. 請使用abstract class設計一個名為Food(食物)的類別，
    其屬性與方法要求如下:

2. 資料屬性:

   1. amount，整數(int)型態，代表食物的份量(以公克為單位)。
   2. calorie，整數(int)型態，代表每一公克的食物所具備的熱量。
    
3. 方法:

    1. Food，建構方法(constructor)，傳入一個整數(int)代表食物
       的份量(以公克為單位)。
    2. setCaloriePerGram，傳入一個整數(int)表示每一公克的食物
       所具備的熱量。
    3. getAmount，傳回食物的份量(以公克為單位)。
    4. getCalorie，傳回食物的熱量(每公克熱量*食物份量)。    

4. 利用所設計的Food抽象類別，請設計出以下的類別並且新增對應的物件
    呼叫getAmount與getCalorie方法後印出傳回值。

<table border=1>
<th>類別名稱</th><th>份量(公克)</th><th>單位熱量(每公克)</th><tr>
<td>Rice</td><td>100</td><td>1</td><tr>
<td>Egg</td><td>30</td><td>2</td><tr>
<td>Cabbage</td><td>50</td><td>1</td><tr>
<td>ProkRib</td><td>300</td><td>10</td><tr>
<td>Carrot</td><td>100</td><td>1</td><tr>
</table>

中

程式及輸出全部正確：10分

輸出正確，但有重複的程式碼：5分

## 執行結果

```
100 grams of rice has 100 calories.
30 grams of egg has 60 calories.
50 grams of cabbage has 50 calories.
300 grams of pork rib has 3000 calories.
100 grams of carrot has 100 calories.
```

## 程式碼

JPA06_1.java

```java
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

class JPA06_1 {
    public static void main(String args[]) {
        Rice rice = new Rice(100);
        System.out.println( rice.getAmount() + " grams of rice has " + rice.getCalorie() + " calories.");
        
        Egg egg = new Egg(30);
        System.out.println( egg.getAmount() + " grams of egg has " + egg.getCalorie() + " calories.");
        
        Cabbage cabbage = new Cabbage(50);
        System.out.println( cabbage.getAmount() + " grams of cabbage has " + cabbage.getCalorie() + " calories.");
        
        PorkRib porkRib = new PorkRib(300);
        System.out.println( porkRib.getAmount() + " grams of pork rib has " + porkRib.getCalorie() + " calories.");
        
        Carrot carrot = new Carrot(100);
        System.out.println( carrot.getAmount() + " grams of carrot has " + carrot.getCalorie() + " calories.");  
    }
}
```

## 開始練習

```java
...

class JPD06_1 {
    public static void main(String args[]) {
        Rice rice = new Rice(100);
        System.out.println( rice.getAmount() + " grams of rice has " + rice.getCalorie() + " calories.");
        
        Egg egg = new Egg(30);
        System.out.println( egg.getAmount() + " grams of egg has " + egg.getCalorie() + " calories.");
        
        Cabbage cabbage = new Cabbage(50);
        System.out.println( cabbage.getAmount() + " grams of cabbage has " + cabbage.getCalorie() + " calories.");
        
        PorkRib porkRib = new PorkRib(300);
        System.out.println( porkRib.getAmount() + " grams of pork rib has " + porkRib.getCalorie() + " calories.");
        
        Carrot carrot = new Carrot(100);
        System.out.println( carrot.getAmount() + " grams of carrot has " + carrot.getCalorie() + " calories.");  
    }
}
```
