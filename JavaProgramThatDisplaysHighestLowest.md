package java2dhighestlowest;

import java.util.Scanner;

public class Java2dHighestLowest {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int row = 1;
        int col = 12;
        int[][] arr = new int[row][col];
        int max = arr[0][0];

        for (int i = 0; i < row; i++) {
            System.out.println("Enter " + col + " numbers: ");
            for (int j = 0; j < 12; j++) {
                arr[i][j] = sc.nextInt();
            }
        }

        for (int i = 0; i < row; i++) {
            for (int j = 0; j < col; j++) {
                if (arr[i][j] > max) {
                    max = arr[i][j];
                }
            }
        }
        System.out.println("Highest is: " + max);
        int min = arr[0][0];
        for (int i = 0; i < row; i++) {
            for (int j = 0; j < col; j++) {
                if (arr[i][j] < min) {
                    min = arr[i][j];
                }
            }
        }
        System.out.println("Lowest is: " + min);
    }

}
