#import tkinter
from tkinter import *
import tkinter.messagebox

#define constants used for fonts
HEADER_FONT = "Arial", 14
BUTTON_FONT = "Arial", 10
NORMAL_FONT = "Arial", 12 
PROMPT_FONT = "Arial", 12, "italic"

#declared these as global variables to be accessible and keep consistency throughout all of the classes
CHECKING_BALANCE = 150.00
SAVINGS_BALANCE = 500.00

#define main class
class BankManager:
    def __init__(self):
        window = Tk()
        window.title("Friendly Bank")
        window["bg"] = "dark olive green"

        welcome = Label(window, text = "Welcome to the Friendly Bank account manager app!", font = HEADER_FONT, fg = "gray99")
        welcome.grid(row = 0, column = 0, columnspan = 4)
        welcome["bg"] = "dark olive green"
        
        balance = Button(window, text = "Check account balance", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = BalancePage)
        balance.grid(row = 1, column = 0)

        deposit = Button(window, text = "Make a deposit", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = DepositPage)
        deposit.grid(row = 1, column = 1)

        withdrawal = Button(window, text = "Make a withdrawal", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = WithdrawalPage)
        withdrawal.grid(row = 1, column = 2)

        transfer = Button(window, text = "Make a transfer", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = TransferPage)
        transfer.grid(row = 1, column = 3)

        window.mainloop()
        #add image to welcome screen
        #moneyPic = PhotoImage(file = "F:\money-2724241_960_720.gif")
        #label = Label(image = moneyPic)
        #label.image = moneyPic
        #label.grid(row = 3, column = 0, columnspan = 4)  

#create window to see balance of accounts
class BalancePage:
    def __init__ (self):
        self.window = Toplevel()
        self.window.title("Balance")
        self.window["bg"] = "dark olive green"
        
        checkBalance = Label(self.window, text = "What account would you like to view?", font = HEADER_FONT, fg = "gray99")
        checkBalance.grid(row = 0, column = 0, columnspan = 2)
        checkBalance["bg"] = "dark olive green"

        #found online the lambda expression allows you to pass an argument while calling a method in the command.
        #did this so could differentiate and tell the program where to go and still close the window
        checkingBtn = Button(self.window, text = "Checking Account", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = lambda:self.closeWindow('checking'))
        checkingBtn.grid(row = 1, column = 0)
        
        savingsBtn = Button (self.window, text = "Savings Account", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = lambda:self.closeWindow('savings'))
        savingsBtn.grid(row = 1, column = 1)

    def closeWindow(self,value):
        if(value == 'savings'):
            balanceSavings()
        else:
            balanceChecking()
        self.window.destroy()

#create window to make deposits
class DepositPage:
    def __init__(self):
        self.window = Toplevel()
        self.window.title("Deposits")
        self.window["bg"] = "dark olive green"
        
        makeDeposit = Label(self.window, text = "Where would you like to make the deposit?", font = HEADER_FONT, fg = "gray99")
        makeDeposit.grid(row = 0, column = 0, columnspan = 2)
        makeDeposit["bg"] = "dark olive green"

        savingsBtn = Button(self.window, text = "Savings Account", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = lambda:self.closeWindow('savings'))
        savingsBtn.grid(row = 1, column = 0)

        checkingBtn  = Button(self.window, text = "Checking Account", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = lambda:self.closeWindow('checking'))
        checkingBtn.grid(row = 1, column = 1)

    def closeWindow(self,value):
        if(value == 'savings'):
            balanceSavings()
        else:
            balanceChecking()
        self.window.destroy()
        


#create window to make withdrawals
class WithdrawalPage:
    def __init__ (self):
        self.window = Toplevel()
        self.window.title("Withdrawals")
        self.window["bg"] = "dark olive green"
        
        label = Label (self.window, text = "What account would you like to make a withdrawal from?", font = HEADER_FONT, fg = "gray99")
        label.grid(row = 0, column = 0, columnspan = 2)
        label["bg"] = "dark olive green"
        
        checkingBtn = Button(self.window, text = "Checking Account", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = lambda:self.closeWindow('checking'))
        checkingBtn.grid(row = 1, column = 0)
        
        savingsBtn = Button (self.window, text = "Savings Account", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = lambda:self.closeWindow('savings'))
        savingsBtn.grid(row = 1, column = 1)

    def closeWindow(self,value):
        if(value == 'savings'):
            withdrawlSavings()
        else:
            withdrawlChecking()
        self.window.destroy()

#create window for transfer
class TransferPage:
    def __init__ (self):
        self.window = Toplevel()
        self.window.title("Transfers")
        self.window["bg"] = "dark olive green"
        
        transBalance = Label(self.window, text = "Which account would you like to make a transfer from?", font = HEADER_FONT, fg = "gray99")
        transBalance.grid(row = 0, column = 0, columnspan = 2)
        transBalance["bg"] = "dark olive green"
        
        checkingBtn = Button(self.window, text = "Checking Account", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = lambda:self.closeWindow('checking'))
        checkingBtn.grid(row = 1, column = 0)
        
        savingsBtn = Button(self.window, text = "Savings Account", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = lambda:self.closeWindow('savings'))
        savingsBtn.grid(row = 1, column = 1)

    def closeWindow(self,value):
        if(value == 'savings'):
            transfromSavings()
        else:
            transfromChecking()
        self.window.destroy()


#############################################

# transfer from savings into checking
class transfromSavings:
    def __init__(self):
        self.window = Toplevel()
        self.window.title("Savings Account")
        self.window["bg"] = "dark olive green"
        
        label = Label(self.window, text = "How much would you like to transfer into your checking?", font = PROMPT_FONT, fg = "gray99")
        label.pack()
        label["bg"] = "dark olive green"

        self.withdrawlAmount = StringVar()
        entrySavings = Entry(self.window, textvariable = self.withdrawlAmount)
        entrySavings.pack()

        submitBtn = Button(self.window, text = "Submit", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = self.transfromSavings)
        submitBtn.pack()

    def transfromSavings(self):
        global SAVINGS_BALANCE
        global CHECKING_BALANCE
        if(float(self.transAmount.get()) > 0):
            (SAVINGS_BALANCE - float(self.transAmount.get())) + (float (self.transAmount.get()) + CHECKING_BALANCE)
            tkinter.messagebox.showinfo("Transfered", "Transfer successful! " + "savings $" + str(SAVINGS_BALANCE) +
                    " checking $" + str(CHECKING_BALANCE))
        self.window.destroy()
        
# withdraw from savings account
class withdrawlSavings:
    def __init__(self):
        self.window = Toplevel()
        self.window.title("Savings Account")
        self.window["bg"] = "dark olive green"
        
        label = Label(self.window, text = "How much would you like to withdrawl?", font = PROMPT_FONT, fg = "gray99")
        label.pack()
        label["bg"] = "dark olive green"

        self.withdrawlAmount = StringVar()
        entrySavings = Entry(self.window, textvariable = self.withdrawlAmount)
        entrySavings.pack()

        submitBtn = Button(self.window, text = "Submit", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = self.withdrawlSavings)
        submitBtn.pack()

    def withdrawlSavings(self):
        global SAVINGS_BALANCE
        global CHECKING_BALANCE
        if(float(self.withdrawlAmount.get()) > 0):
            SAVINGS_BALANCE -= float(self.withdrawlAmount.get())
            tkinter.messagebox.showinfo("Withdrawn", "Withdrawl successful! " + "savings $" + str(SAVINGS_BALANCE) +
                    " checking $" + str(CHECKING_BALANCE))
        self.window.destroy()

#create window to see balance for savings account
class balanceSavings:
    def __init__(self):
        self.window = Toplevel()
        self.window.title("Savings Account")
        self.window["bg"] = "dark olive green"
        
        label = Label(self.window, text = "Would you like to view your savings account?", font = PROMPT_FONT, fg = "gray99")
        label.pack()
        label["bg"] = "dark olive green"

        self.depositAmount = StringVar()
        entrySavings = Entry(self.window, textvariable = self.depositAmount)
        entrySavings.pack()

        submitBtn = Button(self.window, text = "Yes", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = self.viewSavings)
        submitBtn.pack()

    def viewSavings(self):
        global SAVINGS_BALANCE
        tkinter.messagebox.showinfo("Savings", "Your balance in " + "savings is $" + str(SAVINGS_BALANCE))
        self.window.destroy()
                

#create window to deposit into savings account
class SavingsPage:
    def __init__(self):
        self.window = Toplevel()
        self.window.title("Savings Account")
        self.window["bg"] = "dark olive green"
        
        label = Label(self.window, text = "How much would you like to deposit?", font = PROMPT_FONT, fg = "gray99")
        label.pack()
        label["bg"] = "dark olive green"

        self.depositAmount = StringVar()
        entrySavings = Entry(self.window, textvariable = self.depositAmount)
        entrySavings.pack()

        submitBtn = Button(self.window, text = "Submit", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = self.addToSavings)
        submitBtn.pack()

    def addToSavings(self):
        global SAVINGS_BALANCE
        global CHECKING_BALANCE
        if(float(self.depositAmount.get()) > 0):
            SAVINGS_BALANCE += float(self.depositAmount.get())
            tkinter.messagebox.showinfo("Deposit", "Deposit successful! " + "savings $" + str(SAVINGS_BALANCE) +
                    " checking $" + str(CHECKING_BALANCE))
        self.window.destroy()

#################################
        
#create window to see balance for checking account
class balanceChecking:
    def __init__(self):
        self.window = Toplevel()
        self.window.title("Checking Account")
        self.window["bg"] = "dark olive green"
        
        label = Label(self.window, text = "Would you like to view your Checking account?", font = PROMPT_FONT, fg = "gray99")
        label.pack()
        label["bg"] = "dark olive green"

        self.depositAmount = StringVar()
        entrySavings = Entry(self.window, textvariable = self.depositAmount)
        entrySavings.pack()

        submitBtn = Button(self.window, text = "Yes", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = self.viewChecking)
        submitBtn.pack()

    def viewChecking(self):
        global CHECKING_BALANCE
        tkinter.messagebox.showinfo("Checking", "Your balance in " + "checking is $" + str(CHECKING_BALANCE))
        self.window.destroy()
                
            
# withdraw from checking account
class withdrawlChecking:
    def __init__(self):
        self.window = Toplevel()
        self.window.title("Checking Account")
        self.window["bg"] = "dark olive green"
        
        label = Label(self.window, text = "How much would you like to withdrawl?", font = PROMPT_FONT, fg = "gray99")
        label.pack()
        label["bg"] = "dark olive green"

        self.withdrawlAmount = StringVar()
        entrySavings = Entry(self.window, textvariable = self.withdrawlAmount)
        entrySavings.pack()

        submitBtn = Button(self.window, text = "Submit", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = self.withdrawlChecking)
        submitBtn.pack()

    def withdrawlChecking(self):
        global SAVINGS_BALANCE
        global CHECKING_BALANCE
        if(float(self.withdrawlAmount.get()) > 0):
            CHECKING_BALANCE -= float(self.withdrawlAmount.get())
            tkinter.messagebox.showinfo("withdrawn", "withdrawl successful! " + "savings $" + str(SAVINGS_BALANCE) +
                    " checking $" + str(CHECKING_BALANCE))
        self.window.destroy()
        
#create window to deposit into checking account
class CheckingPage:
    def __init__(self):
        self.window = Toplevel()
        self.window.title("Checking Account")
        self.window["bg"] = "dark olive green"
        
        label = Label(self.window, text = "How much would you like to deposit?", font = PROMPT_FONT, fg = "gray99")
        label.pack()
        label["bg"] = "dark olive green"
        
        self.depositAmount = StringVar()
        entrySavings = Entry(self.window, textvariable = self.depositAmount)
        entrySavings.pack()

        submitBtn = Button(self.window, text = "Submit", font = BUTTON_FONT, bg = "olive drab", fg = "gray99", command = self.addToChecking)
        submitBtn.pack()

    def addToChecking(self):
        global SAVINGS_BALANCE
        global CHECKING_BALANCE
        if(float(self.depositAmount.get()) > 0):
            CHECKING_BALANCE += float(self.depositAmount.get())
            tkinter.messagebox.showinfo("Deposit", "Deposit successful! " + "savings $" + str(SAVINGS_BALANCE) +
                    " checking $" + str(CHECKING_BALANCE))
        self.window.destroy()
        
        
        
BankManager()
