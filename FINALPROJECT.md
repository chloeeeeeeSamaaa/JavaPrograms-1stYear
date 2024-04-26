
import java.util.Scanner;

public class FoodManagement {

    private int balance = 100;
    private int chickenPrice = 50;
    //pbulic int beefPrice = 60;
    public static String pass = "";
    public static int pins;
    
    public void processPurchase(int itemPrice, String itemName) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Buy " + itemName + "? (Y/N): ");
        String response = sc.next();
        if (response.equalsIgnoreCase("Y")) {
            if (itemPrice <= balance) {
                balance -= itemPrice;
                System.out.println("Successfully bought " + itemName);
                System.out.println("Remaining balance: " + balance);
            } else {
                System.out.println("Insufficient balance");
            }
        } else {
            System.out.println("Not bought");
        }
    }

    public static void main(String[] args) {
        FoodManagement foodManager = new FoodManagement();
        Scanner sc = new Scanner(System.in);
        int pin;
        int choice;
        
        System.out.println("Create account");
        System.out.println("Enter username: ");
        String newpass = sc.nextLine();
        pass = newpass;
        System.out.println("Enter pin");
        int gg = sc.nextInt();
        pins = gg;
        String ha;
        do {
            System.out.println("Input username: ");
            ha = sc.nextLine();
            if (pass.equals(ha)) {
                System.out.println("Matched");
                break;
            } else {
                System.out.println("Incorrect");
            }
        } while (pass != ha);
       int shet;
          do {
            System.out.println("Input pin: ");
             shet = sc.nextInt();
           
            if (pass.equals(gg)) {
                System.out.println("Matched");
                break;
            } else {
                System.out.println("Incorrect");
            }
        } while (pins != shet);
    

        // Main menu
        while (true) {
            System.out.println("1. Chicken [" + foodManager.chickenPrice + "]");
            //   System.out.println("2. Beef [" + foodManager.beefPrice + "]");
            System.out.println("3. Exit");
            System.out.println("Enter choice: ");
            choice = sc.nextInt();

            switch (choice) {
                case 1:

                    foodManager.processPurchase(foodManager.chickenPrice, "chicken");
                    break;
                case 2:
                    //      foodManager.processPurchase(foodManager.beefPrice, "beef");
                    break;
                case 3:
                    System.exit(0);
                    break;
                default:
                    System.out.println("Invalid choice");
            }
        }
    }
}
