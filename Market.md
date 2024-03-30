package marketprogram;

import java.util.Scanner;

public class MarketProgram {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int pin;

        do {
            System.out.println("Enter Pin: ");
            pin = sc.nextInt();
            if (pin != 1234) {
                System.out.println("Incorrect PIN. Try again.");
            }
        } while (pin != 1234);
        
        int balance = 500;
        while (true) {
            int deposit = 0;
            System.out.println("FreshCart");
            System.out.println("Balance: "+balance);
            System.out.println("[1] Meat");
            System.out.println("[2] Vegetables");
            System.out.println("[3] Deposit");
            System.out.println("[4] Exit");
            System.out.println("Enter choice: ");
            int choice = sc.nextInt();

            switch (choice) {
                case 1:
                    System.out.println("[1] Chicken meat [50]");
                    System.out.println("[2] Pork meat [60]");
                    System.out.println("[3] Beef [70]");
                    System.out.println("Enter choice: ");
                    int m = sc.nextInt();
                    switch (m) {
                        case 1:
                            if (balance >= 50) {
                                balance -= 50;
                                System.out.println("Successfully bought chicken meat, Balance is now " + balance + ".");
                            } else {
                                System.out.println("Insufficient balance");
                            }
                            break;
                        case 2:
                            if (balance >= 60) {
                                balance -= 60;
                                System.out.println("Successfully bought pork meat, Balance is now " + balance + ".");
                            } else {
                                System.out.println("Insufficient balance");
                            }
                            break;
                        case 3:
                            if (balance >= 70) {
                                balance -= 70;
                                System.out.println("Successfully bought beef, Balance is now " + balance + ".");
                            } else {
                                System.out.println("Insufficient balance.");
                            }
                            break;
                        default:
                            System.out.println("Invalid choice.");
                    }
                    break;
                case 2:
                    System.out.println("[1] Carrots [50]");
                    System.out.println("[2] Papaya  [60]");
                    System.out.println("Enter choice: ");
                    int v = sc.nextInt();

                    switch (v) {
                        case 1:
                            if (balance >= 50) {
                                balance -= 50;
                                System.out.println("Successfully bought carrots, Balance is now " + balance + ".");
                            } else {
                                System.out.println("Insufficient balance.");
                            }
                            break;
                        case 2:
                            if (balance >= 60) {
                                balance -= 60;
                                System.out.println("Successfully bought papaya, Balance is now " + balance + ".");
                            } else {
                                System.out.println("Insufficient balance.");
                            }
                            break;
                        default:
                            System.out.println("Invalid choice.");
                            break;
                    }
                    break;
                case 3:
                    System.out.println("Enter an amount to deposit: ");
                    deposit = sc.nextInt();
                    balance+=deposit;
                    System.out.println("Succesfully deposited "+deposit+" balance is now "+balance+".");
                    break;
                case 4:
                    System.out.println("Exiting thank you for using this program...");
                    System.exit(0);
                    break;
                default:
                    System.out.println("Invalid choice.");
            }
        }
    }
}
