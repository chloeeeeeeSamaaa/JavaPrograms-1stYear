import java.util.Scanner;

// Base class: Calculation
class Calculation {
    int z;

    public void addition(int x, int y) {
        z = x + y;
        System.out.println("The sum of the given numbers: " + z);
    }

    public void subtraction(int x, int y) {
        z = x - y;
        System.out.println("The difference between the given numbers: " + z);
    }
}

// Derived class: MyCalculation
public class MyCalculation extends Calculation {
    public void multiplication(int x, int y) {
        z = x * y;
        System.out.println("The product of the given numbers: " + z);
    }

    public void division(int x, int y) {
        if (y!= 0) {
            z = x / y;
            System.out.println("The quotient of the given numbers: " + z);
        } else {
            System.out.println("Error! Division by zero is not allowed.");
        }
    }

    public static void main(String args[]) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter the first number:");
        int a = scanner.nextInt();

        System.out.println("Enter the second number:");
        int b = scanner.nextInt();

        System.out.println("Enter the operator (+, -, *, /):");
        char operator = scanner.next().charAt(0);

        MyCalculation demo = new MyCalculation();

        switch (operator) {
            case '+':
                demo.addition(a, b);
                break;
            case '-':
                demo.subtraction(a, b);
                break;
            case '*':
                demo.multiplication(a, b);
                break;
            case '/':
                demo.division(a, b);
                break;
            default:
                System.out.println("Invalid operator. Please enter either +, -, * or /.");
        }
    }
}
