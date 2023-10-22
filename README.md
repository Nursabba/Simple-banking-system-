# Simple-banking-system-
codeAlpha 
package CodeAlpha;

import java.util.Scanner;

public class SimpleBankingApplication {
    public static void main(String[] args) {
        Scanner sc= new Scanner(System.in);
        BankAccount bank1=new BankAccount("Gopal Kumar","01");
        bank1.showMenu();
    }
}
class BankAccount{
    int balance ;
    String customerName;
    String customerId;
    BankAccount(String cname,String cid){
        customerName=cname;
        customerId=cid;
    }
    void deposite (int amount){
        if(amount!=0){
            balance=balance+amount;
        }
    }
    void withdraw(int amount){
        if(amount!=0){
            balance=balance-amount;
        }
    }
    void showMenu(){
        char option='\0';
        Scanner sc=new Scanner(System.in);
        System.out.println("Welcome "+customerName);
        System.out.println("your id is : "+customerId);
        System.out.println();
        System.out.println("A. Check balance");
        System.out.println("B.Deposit");
        System.out.println("C.Withdraw ");
        System.out.println("D.Exit");

        do{
            System.out.println("=====-==================");
            System.out.println("Enter the option");
            System.out.println("========================");
            option=sc.next().charAt(0);
            //  Character.toUpperCase(option);
            switch (option) {
                case 'A':
                    System.out.println("=====-==================");
                    System.out.println("Balance is : " + balance);
                    System.out.println("=====-==================");
                    System.out.println();
                    break;
                case 'B':
                    System.out.println("=====-==================");
                    System.out.println("Enter the Deposit amount is ");
                    System.out.println("=====-==================");
                    int amount = sc.nextInt();
                    deposite(amount);
                    System.out.println();
                    break;
                case 'C':
                    System.out.println("=====-==================");
                    System.out.println("Enter the withdraw amount is ");
                    System.out.println("=====-==================");
                    int amount2 = sc.nextInt();
                    withdraw(amount2);
                    System.out.println();
                    break;
                case 'D':
                    System.out.println("==========================");
                    break;
                default:
                    System.out.println("Invalid option please try again");
                    break;
            }
        }while (option!='D');
    }
}
