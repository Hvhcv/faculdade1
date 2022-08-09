


package com.mycompany.apliccation;

import com.mycompany.entities.account.BusinessAccount;
import com.mycompany.entities.account.SavingsAccounts;
import com.mycompany.entities.account.account;


public class Program {

    public static void main(String[] args) {
        account acc1 = new account(1001,"Alex",1000.0);
        BusinessAccount bacc = new BusinessAccount(500.0,1002,"Maria",0.0);
        //Upcasting
        account acc6= bacc;
        account acc2 = new BusinessAccount(200.0, 1004, "Bob", 0.0);
        account acc3 = new SavingsAccounts(0.0, 1004, "Anna", 0.01);
        //downcasting
        
        BusinessAccount acc4 = (BusinessAccount) acc2;
        acc4.loan(100.00);
        
        //CUIDADO COM A CONVERSAO ERRO DE DOWNCASTING COMPILADOR NAO AVISA
       //BusinessAccount acc5 = (BusinessAccount) acc3;
       
        //instanceof: serve para TESTAR se o DOWNCAST e compativel
        if (acc3 instanceof BusinessAccount){
            BusinessAccount acc5 = (BusinessAccount) acc3;
            acc5.loan(500.0);
            System.out.println("Loan");
        }
        if (acc3 instanceof SavingsAccounts){
            SavingsAccounts acc5 = (SavingsAccounts)acc3;
            acc5.updateBalance();
        }
        acc1.withdraw(200.0);
        System.out.println(acc1.getBalance());
        
        account acc7 = new SavingsAccounts(0.01, 1007, "Maria", 1000.0);
        acc7.withdraw(200.0);
        System.out.println(acc2.getBalance());
        System.out.println("andre");
    }
}
