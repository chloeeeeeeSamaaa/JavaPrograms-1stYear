
import java.util.Scanner;
public class Registration {
     private static String[][] registeredUsers = new String[100][2];
     private static int usercount = 0;

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String username;
        int pin;
        int choice;
        do{
        System.out.println("Simple Registration System");
        System.out.println("1.Register");
        System.out.println("2.Display");
        System.out.println("3.Exit");
        System.out.println("Enter choice: ");
        choice = sc.nextInt();
        switch(choice){
            case 1:
                 System.out.println("Enter username: ");
                    username = sc.next();
                    if (isUsernameTaken(username)) {
                        System.out.println("Username already taken. Please choose a different one.");
                    } else {
                        System.out.println("Enter pin: ");
                        pin = sc.nextInt();
                        register(username, pin);
                    }
                    break;
                case 2:
                    display();
                    break;
                    case 3:
                        System.out.println("Exit");
        }
        }while(choice != 3);
    }
    public static void register(String username, int pin){
        if(usercount >= registeredUsers.length){
            return;
        }
        registeredUsers[usercount][0] = username;
        registeredUsers[usercount][1] = String.valueOf(pin);
        usercount++;
      System.out.println("User registered");
    }
    
    public static void display(){
        if(usercount == 0){
            System.out.println("No users registered");
        }else{
            System.out.println("Registered Users");
            for(int i = 0; i < usercount; i++){
                System.out.println("Username: "+registeredUsers[i][0]+"\nPin: "+registeredUsers[i][1]);
            }
        }
    }
    
      public static boolean isUsernameTaken(String username) {
        for (int i = 0; i < usercount; i++) {
            if (registeredUsers[i][0].equals(username)) {
                return true;
            }
        }
        return false;
      }
    
    
}
