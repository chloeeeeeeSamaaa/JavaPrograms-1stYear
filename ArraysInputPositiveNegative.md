
import java.util.Scanner;
class HelloWorld {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter value of array: ");
        int n = sc.nextInt();
        int arr [] = new int [n];
        System.out.println("Enter "+n+" numbers: ");
        for(int i = 0; i<n;i++){
            arr[i] = sc.nextInt();
        }
        System.out.println("Positive numbers: ");
        for(int eme: arr){
            if(eme>=0){
                System.out.println(" "+eme);
            }
        }
        System.out.println("Negative numbers: ");
        for(int eme: arr){
            if(eme<=0){
                System.out.println(" "+eme);
            }
        }
}
}
