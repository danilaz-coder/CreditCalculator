import java.util.Scanner;

public class CreditCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Введите сумму кредита: ");
        double loanAmount = scanner.nextDouble();

        System.out.print("Введите годовую процентную ставку: ");
        double annualInterestRate = scanner.nextDouble();

        System.out.print("Введите срок кредита (в месяцах): ");
        int loanTermInMonths = scanner.nextInt();

        double monthlyInterestRate = annualInterestRate / 12 / 100;
        double monthlyPayment = calculateMonthlyPayment(loanAmount, monthlyInterestRate, loanTermInMonths);

        System.out.println("Ежемесячный платеж: " + monthlyPayment);
        System.out.println("Общая сумма выплат: " + (monthlyPayment * loanTermInMonths));
        System.out.println("Общая сумма переплаты: " + ((monthlyPayment * loanTermInMonths) - loanAmount));

        scanner.close();
    }

    public static double calculateMonthlyPayment(double loanAmount, double monthlyInterestRate, int loanTermInMonths) {
        double monthlyPayment;
        monthlyPayment = (loanAmount * monthlyInterestRate) / (1 - Math.pow(1 + monthlyInterestRate, -loanTermInMonths));
        return monthlyPayment;
    }
}

