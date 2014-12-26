# 題目四

(1) Peter決定買入B基金2000元，買價50元；C基金5000元，買價30元。

(2) 請查詢peter之活期存款戶的餘額及每筆基金的單位數。 

(3) 基金B的價格現在漲到100，請查詢基金B的餘額。 
     請使用FundAccount及HashMap設計一支援買多筆基金（multiFund）的類別。 
     HashMap 的 key 值為基金名稱 (String)，value值為 FundAccount，
     使其代入 B 基金後，可輸出目前 B 基金的金額。 

## 執行結果

```
活期餘額：10593
A:0.0
B:40.0
C:166.66666666666666
B 基金餘額: 4000
```

## 程式碼

JPA06_4.java

```java
import java.util.*;

class Account{
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
		balance-=n;
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
		this.duration=duration;
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
        if (specialAccount.isExempt()) {
			freeAccount.withdraw(among);
		} else {
			freeAccount.withdraw((int)(among * 1.02));
		}
		unit+=(double)among / price;
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
			System.out.println(fund.fundName+ ":" + fund.getUnit());
		}
	}
    
    int getFundBalance(String name, int price) {
        return funds.get(name).balance(price);
    }
}

class JPA06_4 {
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
        
		MultiFund multi = new MultiFund();
		multi.addFund("A", fund);
		FundAccount fundB = new FundAccount("peter", "B", free, special);
		fundB.buy(2000, 50);
		multi.addFund("B", fundB);
		FundAccount fundC = new FundAccount("peter", "C", free, special);
		fundC.buy(5000, 30);
		multi.addFund("C", fundC);
		System.out.println("活期餘額：" + free.balance());
		multi.printEachUnit();
       	System.out.println("B 基金餘額: " + multi.getFundBalance("B", 100));
    }
}
```

## 開始練習

```java
//...

class JPD06_4 {
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
        
		MultiFund multi = new MultiFund();
		multi.addFund("A", fund);
		FundAccount fundB = new FundAccount("peter", "B", free, special);
		fundB.buy(2000, 50);
		multi.addFund("B", fundB);
		FundAccount fundC = new FundAccount("peter", "C", free, special);
		fundC.buy(5000, 30);
		multi.addFund("C", fundC);
		System.out.println("活期餘額：" + free.balance());
		multi.printEachUnit();
       	System.out.println("B 基金餘額: " + multi.getFundBalance("B", 100));
    }
}
```
