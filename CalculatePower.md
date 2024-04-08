
import java.util.Scanner;
class Power {
    public static int power(int base,int exponent){
        int power = 1;
        for(int i = 0;i<exponent;i++){
            power = power*base;
        }
        return power;
    }
    public static void main(String[] args) {
       Scanner sc = new Scanner(System.in);
        System.out.println("Enter base: ");
        int base = sc.nextInt();
        System.out.println("Enter exponent: ");
        int exponent = sc.nextInt();
        int eme = power(base,exponent);
        System.out.println(" "+base+" to the power of "+exponent+" is "+eme);
    }
}
