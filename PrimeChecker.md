import java.util.Scanner;

public class HelloWorld {
    public static int prime(int n){
        if(n<=1){
            return 0;
        }
        for(int i = 2;i*i<=n;i++){
            if(n % i == 0){
                return 0;
            }
        }
        return 1;
    }
    
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        while(true){
            System.out.println("Enter number: ");
            int n = sc.nextInt();
            if(prime(n)==1){
                System.out.println(n+" is prime");
            }else{
                System.out.println(n+" is not prime");
            }
        }
    }
}
