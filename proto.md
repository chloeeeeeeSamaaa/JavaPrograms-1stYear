import java.util.Scanner;

public class WaterBillSystemm {
    private String[] customerNames;
    private String[] customerAddresses;
    private double[][] waterConsumption;
    private double[] waterBills;
    private int numCustomers;
    private int numMonths;

    public WaterBillSystemm(int maxCustomers, int maxMonths) {
        customerNames = new String[maxCustomers];
        customerAddresses = new String[maxCustomers];
        waterConsumption = new double[maxCustomers][maxMonths];
        waterBills = new double[maxCustomers];
        numCustomers = 0;
        numMonths = maxMonths;
    }

    public void addCustomer(String name, String address) {
        if (numCustomers < customerNames.length) {
            customerNames[numCustomers] = name;
            customerAddresses[numCustomers] = address;
            numCustomers++;
            System.out.println("Customer added successfully!");
        } else {
            System.out.println("Maximum number of customers reached!");
        }
    }

    public void addCustomer(String name, String address, double initialConsumption) {
        if (numCustomers < customerNames.length) {
            customerNames[numCustomers] = name;
            customerAddresses[numCustomers] = address;
            waterConsumption[numCustomers][0] = initialConsumption;
            numCustomers++;
            System.out.println("Customer added successfully with initial consumption!");
        } else {
            System.out.println("Maximum number of customers reached!");
        }
    }

   public void enterWaterConsumption(int month) {
    Scanner scanner = new Scanner(System.in);
    for (int i = 0; i < numCustomers; i++) {
        double consumption;
        do {
            System.out.print("Enter water consumption for " + customerNames[i] + " in month " + month + ": ");
            while (!scanner.hasNextDouble()) {
                System.out.println("Invalid input. Please enter a number.");
                System.out.print("Enter water consumption for " + customerNames[i] + " in month " + month + ": ");
                scanner.next(); // discard invalid input
            }
            consumption = scanner.nextDouble();
            if (consumption < 0) {
                System.out.println("Water consumption cannot be negative. Please enter a valid value.");
            }
        } while (consumption < 0);
        waterConsumption[i][month - 1] = consumption;
    }
}



    public void calculateWaterBill() {
        for (int i = 0; i < numCustomers; i++) {
            double totalConsumption = 0;
            for (int j = 0; j < numMonths; j++) {
                totalConsumption += waterConsumption[i][j];
            }
            waterBills[i] = calculateBill(totalConsumption);
            System.out.println("Water bill for " + customerNames[i] + ": " + waterBills[i]);
        }
    }

    private double calculateBill(double totalConsumption) {
        if (totalConsumption <= 100) {
            return totalConsumption * 0.5;
        } else if (totalConsumption <= 200) {
            return 50 + (totalConsumption - 100) * 0.75;
        } else {
            return 150 + (totalConsumption - 200) * 1.0;
        }
    }

    public void displayWaterBills() {
        System.out.println("Water Bills:");
        for (int i = 0; i < numCustomers; i++) {
            System.out.println("Customer Name: " + customerNames[i]);
            System.out.println("Address: " + customerAddresses[i]);
            System.out.println("Water Bill: " + waterBills[i]);
            System.out.println();
        }
        double totalBills = 0;
        for (double bill : waterBills) {
            totalBills += bill;
        }
        System.out.println("Total amount to be collected: " + totalBills);
    }

    public double calculateAverageConsumption() {
        double totalConsumption = 0;
        for (int i = 0; i < numCustomers; i++) {
            for (int j = 0; j < numMonths; j++) {
                totalConsumption += waterConsumption[i][j];
            }
        }
        return totalConsumption / (numCustomers * numMonths);
    }

    public double findMaximumConsumption() {
        double maxConsumption = Double.MIN_VALUE;
        for (int i = 0; i < numCustomers; i++) {
            for (int j = 0; j < numMonths; j++) {
                if (waterConsumption[i][j] > maxConsumption) {
                    maxConsumption = waterConsumption[i][j];
                }
            }
        }
        return maxConsumption;
    }

    public double findMinimumConsumption() {
        double minConsumption = Double.MAX_VALUE;
        for (int i = 0; i < numCustomers; i++) {
            for (int j = 0; j < numMonths; j++) {
                if (waterConsumption[i][j] < minConsumption) {
                    minConsumption = waterConsumption[i][j];
                }
            }
        }
        return minConsumption;
    }

   public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);

    System.out.print("Enter the maximum number of customers: ");
    int maxCustomers = scanner.nextInt();
    System.out.print("Enter the number of months: ");
    int maxMonths = scanner.nextInt();

    WaterBillSystemm system = new WaterBillSystemm(maxCustomers, maxMonths);

    char ch;
    
do{
        System.out.println("1. Add Customer");
        System.out.println("2. Enter Water Consumption for Current Month");
        System.out.println("3. Calculate Water Bill");
        System.out.println("4. Display Water Bills");
        System.out.println("5. Calculate Average Consumption");
        System.out.println("6. Find Maximum Consumption");
        System.out.println("7. Find Minimum Consumption");
        System.out.println("8. Exit");
        System.out.print("Enter your choice: ");
        int choice = scanner.nextInt();

        switch (choice) {
            case 1:
                System.out.print("Enter customer name: ");
                String name = scanner.nextLine(); // Consume newline
                name = scanner.nextLine(); // Read the actual input
               
             
                System.out.print("Enter customer address: ");
                String address = scanner.nextLine();
                system.addCustomer(name, address);
                break;
            case 2:
                System.out.print("Enter current month: ");
                int currentMonth = scanner.nextInt();
                system.enterWaterConsumption(currentMonth);
                break;
            case 3:
                system.calculateWaterBill();
                break;
            case 4:
                system.displayWaterBills();
                break;
            case 5:
                System.out.println("Average Consumption: " + system.calculateAverageConsumption());
                break;
            case 6:
                System.out.println("Maximum Consumption: " + system.findMaximumConsumption());
                break;
            case 7:
                System.out.println("Minimum Consumption: " + system.findMinimumConsumption());
                break;
            case 8:
                System.out.println("Process complete.");
                System.exit(0);
                break;
            default:
                System.out.println("Invalid choice!");
        }
        System.out.println("Do you want to perform another operation? (yes/no):");
        ch = scanner.next().charAt(0);
}while(ch == 'y' || ch == 'Y');

    System.out.println("Process complete.");
    scanner.close();
}
}
