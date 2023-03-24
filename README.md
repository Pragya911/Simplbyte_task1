# Simplbyte_task1
import java.util.Date;
import java.util.Scanner;

public class ATM_interface {
    double Balance;
    int Pin;
    int accno;
    Date date;

    public ATM_interface(double Balance,int Pin , int accno){
        this.Balance = Balance;
        this.Pin = Pin;
        this.accno = accno;
    }
    public void Withdraw(double amount){
        if(amount>Balance){
            System.out.println("INSUFFICIANT BALANCE");
        }
        else{
            Balance-=amount;
            System.out.println("Amount Succesfully Withdrawn "+amount);
            System.out.println("Remaining Balance "+Balance);
        }
    }
    public void deposit(int amount){
        Balance+=amount;
        System.out.println("Total Balance "+Balance);
    }
    public void transdet(int accno){
        System.out.println("Transaction Done on "+date+" is "+Balance);
        return;

    }
    public static void main(String[] args) {
        ATM_interface atm = new ATM_interface(50000,1234,565658);
        Scanner sc = new Scanner(System.in);
        System.out.println("PIN : ");
        int a = sc.nextInt();
        if(a!= atm.Pin){
            System.out.println("Incorrect Pin!");
            return;
        }
       while(true) {
           System.out.println(" Press 1 for Withdraw");
           System.out.println(" Press 2 for Diposit");
           System.out.println(" Press 3 for Check balance");
           System.out.println(" Press 4 for Transaction History");
           System.out.println("Press 5 for Exit");


           int choice = sc.nextInt();
           switch (choice) {
               case (1):
                   System.out.print("Enter the Amount:");
                   double penny = sc.nextDouble();
                   atm.Withdraw(penny);
                   System.out.println("Transaction Successful. Reamaining balance " + atm.Balance);
                   break;
               case (2):
                   System.out.print("Enter the amount to be Deposit:");
                   int b = sc.nextInt();
                   atm.deposit(b);
                   System.out.println("Money successfully Deposited.Total Balance " + atm.Balance);
                   break;
               case (3):
                   System.out.println("Balance " + atm.Balance);
                   break;
               case (4):
                   System.out.println("Transaction of Account number 565658 is " +atm.Balance);
                   break;
               case (5):
                   System.out.println("Thanks!");
                   break;
               default:
                   System.out.println("Invalid Details!");
                   break;
           }

       }

    }
}
