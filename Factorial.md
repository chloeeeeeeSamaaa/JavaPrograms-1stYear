
import java.util.Scanner;
class Factorial {
    public static int factorial(int n)
    {
        int result = 1;
        for(int i = n;i>=2;i--){
            result = i*result;
        }
        return result;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter number: ");
        int n = sc.nextInt();
        int eme = factorial(n);
        System.out.println("Factorial of "+n+" is "+eme);
    }
}
