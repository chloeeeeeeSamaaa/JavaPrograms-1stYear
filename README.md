
import java.util.Scanner;
class HelloWorld {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter rows: ");
        int row = sc.nextInt();
        System.out.println("Enter columns: ");
        int col = sc.nextInt();
        int arr [][] = new int [row][col];
        for(int i = 0;i<row;i++){
        System.out.println("Enter "+row+" numbers for row "+i+1+" : ");
        for(int j = 0;j<col;j++){
            arr[i][j] = sc.nextInt();
        }
        }
         System.out.println("Entered rows is "+row+" and columns is "+col);
        for(int i = 0;i<row;i++){
            System.out.println("Numbers entered in row "+(i+1));
            for(int j = 0;j<col;j++){
             System.out.println(" "+arr[i][j]) ;  
            }
        }
        System.out.println();
    }
}
