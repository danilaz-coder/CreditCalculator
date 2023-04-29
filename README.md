import java.util.Scanner;

public class Calcullator {
    public static
    void main ( String[] args ) {
double num1;
double num2;
double ans;
        Scanner reader= new Scanner (System.in);
        System.out.print("Enter two numbers:");
        num1 = reader.nextDouble();
        num2 = reader.nextDouble();
        System.out.print(" \n Enter an operator(+,-,*,/):");
        char op = reader.next().charAt( 0 );
switch (op){
    case '+'-> ans = num1+num2;
    case '-'-> ans = num1-num2;
    case '*'-> ans = num1*num2;
    case '/'-> ans = num1/num2;
    default -> {
        System.out.print( "Error! Error correct operator" );
        return;
    }
}
        System.out.print(" \nThe result is given as follows\n");
        System.out.print(num1 + ""+ op + "" + num2 + " = " + ans );
    }
}
