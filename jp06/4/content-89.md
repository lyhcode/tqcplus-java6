# 題目五

(1) 請使用exception撰寫一功能：當任一帳戶之餘額低於0時，
     不可提款，且印出警告信息。

(2) peter再次購買A基金14000元, 價格為每單位300元。

## 執行結果

```
peter:提款金額: 14280 大於存款餘額: 10593
```

## 程式碼

JPA06_5.java

```java
import java.util.*;

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
	
	void withdraw(int n) throws Exception {
		if (balance < n) {
			throw new Exception(name + ":提款金額: " + n + " 大於存款餘額: " + balance);
		} else {
			balance -= n;
		}
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
	
	void buy(int among, int price) {
		try {
			if (specialAccount.isExempt()) {
				freeAccount.withdraw(among);
			} else {
				freeAccount.withdraw((int)(among * 1.02));
			}
			unit += (double)among / price;
		} catch(Exception e) {
			System.out.println(e.getMessage());
		}
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
	
	double getUnit(){
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
		return deposit.balance+free.balance+special.balance;
	}
}

class MultiFund {
	HashMap<String, FundAccount> funds;
	
	MultiFund() {
		funds = new HashMap<String, FundAccount>();
	}
	
	void addFund(String name, FundAccount fund) {
		funds.put(name, fund);
	}
	
	void printEachUnit() {
		for (FundAccount fund: funds.values()) {
			System.out.println(fund.getUnit());
		}
	}
    
    int getFundBalance(String name, int price) {
        return funds.get(name).balance(price);
    }
}

class JPA06_5 {
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

		try {
			special.withdraw(5000);
			fund.buy(2000, 300);
			
			fund.sell(fund.getUnit(), 400);			

			InternetAccount internet = new InternetAccount();
			internet.setDeposit(deposit);
			internet.setFree(free);
			internet.setSpecial(special);
			internet.setFund(fund);

			MultiFund multi = new MultiFund();
			multi.addFund("A", fund);
			FundAccount fundB = new FundAccount("peter", "B", free, special);
			fundB.buy(2000, 50);
			multi.addFund("B", fundB);
			FundAccount fundC = new FundAccount("peter", "C", free, special);
			fundC.buy(5000, 30);
			multi.addFund("C", fundC);
						
            fund.buy(14000, 300);
            
		} catch(Exception e) {
			System.out.println(e.getMessage());
		}		
	}
}
```

## 開始練習

```java
//...

class JPD06_5 {
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

		try {
			special.withdraw(5000);
			fund.buy(2000, 300);
			
			fund.sell(fund.getUnit(), 400);			

			InternetAccount internet = new InternetAccount();
			internet.setDeposit(deposit);
			internet.setFree(free);
			internet.setSpecial(special);
			internet.setFund(fund);

			MultiFund multi = new MultiFund();
			multi.addFund("A", fund);
			FundAccount fundB = new FundAccount("peter", "B", free, special);
			fundB.buy(2000, 50);
			multi.addFund("B", fundB);
			FundAccount fundC = new FundAccount("peter", "C", free, special);
			fundC.buy(5000, 30);
			multi.addFund("C", fundC);
						
            fund.buy(14000, 300);
            
		} catch(Exception e) {
			System.out.println(e.getMessage());
		}		
	}
}
```
