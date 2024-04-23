import java.util.Scanner;
class calculator{
    public double add(double a, double b){
        return a + b;
    }
    public double subtract(double a,double b){
        return a - b;
    }
}
class overidecalcu extends calculator{
    @Override
     public double add(double a, double b){
        return a + b;
    }
    @Override
    public double subtract(double a,double b){
        return a - b;
    }
    
    public double multiply(double a,double b){
        return a * b;
    }
  
    public double divide(double a,double b){
        if(b != 0 ){
            return a/b;
        }else{
            return 0;
        }
    }
}

 public class Calculator {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        calculator calc = new calculator();
        overidecalcu overcal = new overidecalcu();
        double result = 0;
        System.out.println("Enter number: ");
        double num1 = sc.nextDouble();
        System.out.println("Enter number: ");
        double num2 = sc.nextDouble();
        System.out.println("operator: ");
        char operator = sc.next().charAt(0);
        if(operator == '+'){
             result = calc.add(num1,num2);
        }else if (operator == '-'){
            result = calc.subtract(num1,num2);
        }else if (operator == '*'){
             result = overcal.multiply(num1,num2);
        }else if(operator == '/'){
            result = overcal.divide(num1,num2);
        }else{
            System.out.println("INVALID");
        }
            System.out.println("Result: "+result);
        }
    }
