import java.util.Scanner;

public class simplecalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Welcome to the Simple Calculator!");

        while (true) {
            try {
                System.out.println("\nEnter the first number:");
                double num1 = Double.parseDouble(scanner.nextLine());

                System.out.println("Enter the second number:");
                double num2 = Double.parseDouble(scanner.nextLine());

                System.out.println("Choose an operation: +, -, *, /");
                String operation = scanner.nextLine();

                double result;

                switch (operation) {
                    case "+":
                        result = num1 + num2;
                        System.out.println("Result: " + result);
                        break;
                    case "-":
                        result = num1 - num2;
                        System.out.println("Result: " + result);
                        break;
                    case "*":
                        result = num1 * num2;
                        System.out.println("Result: " + result);
                        break;
                    case "/":
                        if (num2 == 0) {
                            System.out.println("Error: Division by zero is not allowed.");
                        } else {
                            result = num1 / num2;
                            System.out.println("Result: " + result);
                        }
                        break;
                    default:
                        System.out.println("Error: Invalid operation. Please use +, -, *, or /.");
                }
            } catch (NumberFormatException e) {
                System.out.println("Error: Invalid input. Please enter numeric values.");
            }

            System.out.println("Do you want to perform another calculation? (yes/no)");
            String choice = scanner.nextLine().toLowerCase();
            if (!choice.equals("yes")) {
                break;
            }
        }

        System.out.println("Thank you for using the Simple Calculator. Goodbye!");
        scanner.close();
    }
}
