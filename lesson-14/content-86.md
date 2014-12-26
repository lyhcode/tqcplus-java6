# 題目二

(1) peter將其優惠存款戶提款5000元。並再次購買A基金2000元，
     價格為每單位300元。

(2) 請列出該【基金餘額】，及peter之活期存款帳戶【售出前活期餘額】。 

(2) 接著peter將其基金全數賣出，賣價為400元.

(4) 請再次查詢peter之活期存款戶的餘額。 

## 執行結果

```
基金餘額：11000
售出前活期餘額：3360
售出後活期餘額：17733
```

## 程式碼

JPA06_2.java

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
		
	FundAccount(String name, String fundName, FreeAccount freeAccount, SpecialAccount specialAccount){
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

class JPA06_2 {
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
		FundAccount fund = new FundAccount("peter", "A", free, special);
        fund.buy(15000, 500);
       	special.withdraw(5000);
		fund.buy(2000, 300);
		System.out.println("基金餘額：" + fund.balance(300));
		System.out.println("售出前活期餘額：" + fund.freeAccount.balance()); 
        fund.sell(fund.getUnit(), 400);					
		System.out.println("售出後活期餘額：" + fund.freeAccount.balance());
	}
}
```

## 開始練習

```java
//...

class JPD06_2 {
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
		FundAccount fund = new FundAccount("peter", "A", free, special);
        fund.buy(15000, 500);
       	special.withdraw(5000);
		fund.buy(2000, 300);
		System.out.println("基金餘額：" + fund.balance(300));
		System.out.println("售出前活期餘額：" + fund.freeAccount.balance()); 
        fund.sell(fund.getUnit(), 400);					
		System.out.println("售出後活期餘額：" + fund.freeAccount.balance());
	}
}
```
