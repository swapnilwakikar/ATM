# ATM

Python ATM code for Withdraw amount, Check account balance and Deposit amount

print("Welcome to Citi Bank ATM")
restart=("Y")
chances=3
balance=999.12
while chances>=0:
    pin=int(input("Please enter your four digit pin: "))
    if pin==1234:
        print("Pin successfully validated...\n")
        print("What would you like to do ?")
        print("Press 1. Check account balance")
        print("Press 2. Withdraw amount")
        print("Press 3. Deposit cash")
        print("Press 4. Remove card")
        while restart not in ('n','N', 'NO','N'):
            print("Press 1. Check account balance")
            print("Press 2. Withdraw amount")
            print("Press 3. Deposit cash")
            print("Press 4. Remove card")
            option=int(input("what would you like to choose ?"))
            if option==1:
                print("Your current account balance is $",balance)
                restart=input("would you like to go back ?")
                if restart in ('n','N', 'NO','N'):
                    print("Thank you, visit again")
                    break

            elif option==2:
                option2=("y")
                withdrawal=float(input("Enter the amount to withdraw: "))
                balance=balance-withdrawal
                print("Amount withdrawn successfully !")
                print("Remaining balance is $", balance)
                restart = input("would you like to go back ?")
                if restart in ('n','N', 'NO','N'):
                    print("Thank you, visit again")
                    break

            elif option==3:
                pay_in=float(input("Enter amount to deposit: "))
                balance=balance+pay_in
                print(" Your current balance is $", balance)
                if restart in ('n', 'N', 'NO', 'N'):
                    print("Thank you, visit again")
                    break

            elif option==4:
                print("Please wait and collect your card.")
                print(" Thanks for using our service...")
                break

            else:
                print("You have entered wrong choice")

    elif pin!=1234:
        print("Incorrect PIN")
        chances=chances-1
        if chances==0:
            print("You have exceeded the given chances")
            exit()
