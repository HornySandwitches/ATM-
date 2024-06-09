# ATM-
/*
Name: M.Yousuf
Reg: Se231074
Desc: ATM Screen
 */
import java.util.Scanner;
public class Main{
    public static void main(String[] args) {
        ATMInterface op=new ATMOperation();
        int atmNumber=12345;
        int atmPin=123;
        Scanner in=new Scanner(System.in);
        System.out.println("Welcome to ATM Machine");
        System.out.print("Enter Atm Number : ");
        atmNumber=in.nextInt();
        System.out.print("Enter Pin: ");
        atmPin=in.nextInt();
        if((atmPin == atmPin) && (atmNumber == atmNumber)){
            while(true){
                System.out.println("1.View Available Balance\n" +
                        "2.Withdraw Amount\n" +
                        "3.Deposit Amount\n" +
                        "4.View Receipt\n" +
                        "5.Exit");
                System.out.println("Enter Choice : ");
                int ch=in.nextInt();
                if(ch==1){
                    op.viewBalance();
                }
                else if(ch==2){
                    System.out.println("Enter amount to withdraw ");
                    double withdrawAmount=in.nextDouble();
                    op.withdrawAmount(withdrawAmount);
                }
                else if(ch==3){
                    System.out.println("Enter Amount to Deposit :");
                    double depositAmount=in.nextDouble();//5000
                    op.depositAmount(depositAmount);
                }
                else if(ch==4){
                    op.viewMiniStatement();
                }
                else if(ch==5){
                    System.out.println("Collect your ATM Card\n Thank you for using ATM Machine");
                    System.exit(0);
                }
                else
                {
                    System.out.println("Please enter correct choice");
                }
            }
        }
        else{
            System.out.println("Incorrect Atm Number or pin");
            System.exit(0);
        }
    }
}
