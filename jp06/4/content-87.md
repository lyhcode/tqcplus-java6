# 題目三

(1) 該銀行為服務客戶增設網路銀行帳戶，一網路銀行帳戶含有
     某客戶之所有帳戶的資料。

(2) 請為peter開立一網路銀行帳戶，並寫一方法計算peter所有
     存款帳戶（不含基金）的總餘額。 

## 執行結果

```
存款總額：28133
```

## 程式碼

JPA06_3.java

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
		unit+=(double)amont / price;
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

class InternetAccount {
	DepositAccount deposit;
	FreeAccount free;
	SpecialAccount special;
	FundAccount fund;
	
	void setDeposit(DepositAccount deposit) {
		this.deposit = deposit;
	}
	
	void setFree(FreeAccount free) {
		this.free = free;
	}
	
	void setSpecial(SpecialAccount special) {
		this.special = special;
	}
	
	void setFund(FundAccount fund) {
		this.fund = fund;
	}
	
	int getTotalBalance() {
		return deposit.balance + free.balance + special.balance;
	}
}

class JPA06_3 {
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
		fund.sell(fund.getUnit(), 400);					
		
		InternetAccount internet = new InternetAccount();
		internet.setDeposit(deposit);
		internet.setFree(free);
		internet.setSpecial(special);
		internet.setFund(fund);
		System.out.println("存款總額：" + internet.getTotalBalance());
	}
}
```

## 開始練習

```java
//...

class JPD06_3 {
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
		fund.sell(fund.getUnit(), 400);					
		
		InternetAccount internet = new InternetAccount();
		internet.setDeposit(deposit);
		internet.setFree(free);
		internet.setSpecial(special);
		internet.setFund(fund);
		System.out.println("存款總額：" + internet.getTotalBalance());
	}
}
```
