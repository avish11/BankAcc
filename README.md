# BankAcc
Simple bank account

class Account:
    def __init__(self,name,balance,min_balance):
        self.name=name
        self.balance=balance
        self.min_balance=min_balance

    def deposit(self,amount):
        self.balance+=amount

    def withdraw(self,amount):
        if self.balance-amount>=self.min_balance:
            self.balance-=amount
        else:
            print("Not enough balance")

    def statement(self):
        print("Account balance: {}".format(self.balance))

    def __str__(self):
        return("Name:{},Current balance:{}".format(self.name,self.balance))

class Current(Account):
    def __init__(self,name,balance):
        super().__init__(name,balance,min_balance = -1000)



name=input("Enter name: ")
balance=0
x=Current(name,balance)
print(x)
dep=input("Enter money to be deposited: ")
x.deposit(int(dep))
print("Hi {}, your new balance is {}".format(x.name,x.balance))
