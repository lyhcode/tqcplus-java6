# 題目一

請開啟 JPD06_1.java，設計「銀行理財帳戶」程式。銀行共有四種帳戶，需計算目前存款，請依下列題意完成作答。將 JPD06_1.java 內的 class JPD06_1 修改為 class JPA06_1，將檔案另存為 JPA06_1.java 後編譯為 JPA06_1.class，所有題目中有使用到的類別也請編譯後一併儲存。

### 設計說明 ###

1. 銀行共設有四種帳戶，分別是「定期存款」帳戶、「活期存款」帳戶、「優惠存款」帳戶及「基金存款」帳戶。每種帳戶都有開戶人、年利率及帳戶餘額的資料。

2. 每個帳戶都可以存款（deposit）、提款（withdraw）、查詢餘額（balance）、加計利息（addInterest）。 

3. 定期存款（DepositAccount）的年利率分 1、2、3 年期，各為 3%、4%、5%。 

4. 活期存款（FreeAccount）的年利率為 2%。

5. 優惠存款帳戶（SpecialAccount）的利率與活期存款同為 2%，但帳戶存款帳戶餘額若保持在 10,000 元以上，則買賣基金可免手續費（傳回布林值代表可/不可）。
 
6. 基金帳戶（FundAccount）的必要資料有：開戶人、基金名稱、單位數、一個活期存款戶、一個優惠存款戶。買入的手續費為買入金額的 2%，賣出的手續費為賣出金額的 2%。基金存款帳戶可以買、賣、查詢餘額，這幾個功能均需傳入基金目前的價格。買賣基金由活期存款帳戶轉帳。 

7. 請為 Peter 開設一個定期存款帳戶（2 年期，存入 5,000 元）、活期存款帳戶（存入 20,000 元）、優惠存款帳戶（存入 10,000 元）。並加總一年的利息後，再查詢各帳戶的餘額。依序列出「定期存款」、「活期存款」、「優惠存款」目前的餘額。

8. 接著再為 Peter 新開設一個基金存款帳戶，並買入 A 基金 15,000 元，價格為每單位 500 元。於三天後該基金跌價為每單位 300 元，請計算目前基金的現值，及 Peter 活期存款帳戶的餘額。請分別列出「基金現額」以及「活期餘額」。

### 評分項目 ###

1. 程式及輸出全部正確，符合題意要求，若輸出正確，但有重複的程式碼則酌扣 5 分。（配分 10 分）

（總分 10 分）

![uml][1]

  [1]: http://yuml.me/5972161b

## 執行結果

```
定期存款：5200
活期存款：20400
優惠存款：10200
基金現額：9000
活期餘額：5400
```

## 程式碼

JPA06_1.java

```java
class Account {
	String name;
	double rate;
	int balance;
	
	Account(String name, double rate) {
		this.name = name;
		this.rate = rate;
	}
	
	void setRate(double rate) {
		this.rate = rate;
	}
	
	void deposit(int n) {
		balance += n;
	}
	
	void withdraw(int n) {
		balance -= n;
	}
	
	int balance() {
		return balance;
	}
	
	void addInterest() {
		balance *= (rate + 1);
	}
}

class DepositAccount extends Account {
	int duration;
	
	DepositAccount(String name, int duration) {
		super(name, 0);
		double rate = 0;
		this.duration = duration;
		switch (duration) {
			case 1: rate = 0.03; break;
			case 2: rate = 0.04; break;
			case 3: rate = 0.05; break;
		}
		super.setRate(rate);
	}	
}

class FreeAccount extends Account {
	
	FreeAccount(String name) {
		super(name, 0.02);
	}	
}

class SpecialAccount extends Account {
	
	SpecialAccount(String name) {
		super(name, 0.02);
	}
	
	boolean isExempt() {
		if (balance > 10000) {
			return true;
		} else {
			return false;
		}
	}
}

class FundAccount extends Account {
	String fundName;
	FreeAccount freeAccount;
	SpecialAccount specialAccount;
	double unit;
		
	FundAccount(String name, String fundName, FreeAccount freeAccount, SpecialAccount specialAccount) {
		super(name, 0);
		this.fundName = fundName;
		this.freeAccount = freeAccount;
		this.specialAccount = specialAccount;
	}
	
	void buy(int amont, int price) {
		if (specialAccount.isExempt()) {
			freeAccount.withdraw(amont);
		} else {
			freeAccount.withdraw((int)(amont * 1.02));
		}
		unit += (double)amont / price;
	}
	
	void sell(double unit, int price) {
		if (specialAccount.isExempt()) {
			freeAccount.deposit((int)(unit * price));
		} else {
			freeAccount.deposit((int)(unit * price * 0.98));
		}
		this.unit -= unit;
	}
	
	int balance(int price) {
		return (int)(unit * price);
	}
	
	double getUnit() {
		return unit;
	}
}

class JPA06_1 {
	public static void main(String args[]) {
		DepositAccount deposit = new DepositAccount("peter", 2);
		deposit.deposit(5000);
		FreeAccount free = new FreeAccount("peter");
		free.deposit(20000);
		SpecialAccount special = new SpecialAccount("peter");
		special.deposit(10000);
		deposit.addInterest();
		free.addInterest();
		special.addInterest();
        System.out.println("定期存款："+deposit.balance());
		System.out.println("活期存款："+free.balance());
		System.out.println("優惠存款："+special.balance());		
		FundAccount fund = new FundAccount("peter", "A", free, special);
		fund.buy(15000, 500);
		System.out.println("基金現額："+fund.balance(300));
		System.out.println("活期餘額："+fund.freeAccount.balance());
	}
}
```

## 開始練習

```java
//...

class JPD06_1 {
	public static void main(String args[]) {
		DepositAccount deposit = new DepositAccount("peter", 2);
		deposit.deposit(5000);
		FreeAccount free = new FreeAccount("peter");
		free.deposit(20000);
		SpecialAccount special = new SpecialAccount("peter");
		special.deposit(10000);
		deposit.addInterest();
		free.addInterest();
		special.addInterest();
        System.out.println("定期存款：" + deposit.balance());
		System.out.println("活期存款：" + free.balance());
		System.out.println("優惠存款：" + special.balance());		
		FundAccount fund = new FundAccount("peter", "A", free, special);
		fund.buy(15000, 500);
		System.out.println("基金現額：" + fund.balance(300));
		System.out.println("活期餘額：" + fund.freeAccount.balance());
	}
}
```
