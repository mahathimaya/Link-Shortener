import java.util.Scanner;

public class SmartCalculator {
    private double result = 0; // Store the result of calculations
    private String currentInput = ""; // Store current user input

    public void printMenu() {
        System.out.println("Simple Calculator");
        System.out.println("Enter operation: +, -, *, /");
        System.out.println("Type 'C' to clear, 'B' to backspace, or 'exit' to quit.");
        System.out.println("Current input: " + currentInput);
    }

    public void performOperation(String operator) {
        if (currentInput.isEmpty()) return; // No input to operate on

        double number = Double.parseDouble(currentInput);
        switch (operator) {
            case "+": result += number; break;
            case "-": result -= number; break;
            case "*": result *= number; break;
            case "/":
                if (number == 0) {
                    System.out.println("Error: Division by zero.");
                    return;
                }
                result /= number; break;
            default: System.out.println("Invalid operator."); return;
        }
        currentInput = ""; // Clear input after operation
        System.out.println("Result: " + result);
    }

    public void clearInput() {
        currentInput = ""; // Clear input
        System.out.println("Input cleared.");
    }

    public void backspace() {
        if (!currentInput.isEmpty()) {
            currentInput = currentInput.substring(0, currentInput.length() - 1); // Remove last character
            System.out.println("Current input after backspace: " + currentInput);
        }
    }

    public void runCalculator() {
        Scanner scanner = new Scanner(System.in);
        while (true) {
            printMenu();
            String input = scanner.nextLine();

            switch (input.toLowerCase()) {
                case "exit": return; // Exit the loop
                case "c": clearInput(); break;
                case "b": backspace(); break;
                default:
                    if (isOperator(input)) {
                        performOperation(input);
                    } else {
                        currentInput += input; // Append to current input
                    }
            }
        }
    }

    private boolean isOperator(String input) {
        return "+-*/".contains(input); // Check if input is an operator
    }

    public static void main(String[] args) {
        new SmartCalculator().runCalculator(); // Start the calculator
    }
}
