import java.util.Scanner;

public class Fibo {
    public static long fibo(int n){
        if(n<=1){
            return n;
        }
        long a = 0, b = 1, next = 0;
        for(int i = 2; i <= n; i++){
            next = a + b;
            a = b;
            b = next;
        }
        return next;
    }
    
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter number: ");
        int n = sc.nextInt();
        System.out.println("Fibonacci Sequence of "+ n);
        for(int i = 0; i < n; i++){
            long me = fibo(i);
            System.out.println(" "+ me);
        }
    }
}
