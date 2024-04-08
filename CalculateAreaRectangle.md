
import java.util.Scanner;
class CalculateAreaRectangle {
    public static int areaofRectangle(int length,int width){
        return length * width;
    }
    public static void main(String[] args) {
        Scanner sc  = new Scanner(System.in);
        System.out.println("Enter length: ");
        int length  = sc.nextInt();
        System.out.println("Enter width: ");
        int width = sc.nextInt();
        int eme = areaofRectangle(length,width);
        System.out.println("Area of rectangle is "+eme);
    }
}
