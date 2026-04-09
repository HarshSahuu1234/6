import java.util.Scanner;
import java.util.Stack;

public class Valid_If {

    // Check relational operator
    static boolean hasRelationalOperator(String expr) {
        return expr.contains(">") || expr.contains("<") ||
                expr.contains("==") || expr.contains("!=") ||
                expr.contains(">=") || expr.contains("<=");
    }

    // Check balanced parentheses
    static boolean isBalanced(String expr) {
        Stack<Character> stack = new Stack<>();

        for (char ch : expr.toCharArray()) {
            if (ch == '(') stack.push(ch);
            else if (ch == ')') {
                if (stack.isEmpty()) return false;
                stack.pop();
            }
        }
        return stack.isEmpty();
    }

    // Main validation function
    static boolean isValidIf(String expr) {

        expr = expr.trim();

        // Must start with "if"
        if (!expr.startsWith("if")) return false;

        // Must contain '(' and ')'
        int start = expr.indexOf('(');
        int end = expr.lastIndexOf(')');

        if (start == -1 || end == -1 || start >= end) return false;

        // Extract condition inside parentheses
        String condition = expr.substring(start + 1, end).trim();

        if (condition.length() == 0) return false;

        // Check relational operator
        if (!hasRelationalOperator(condition)) return false;

        // Check parentheses balance
        if (!isBalanced(expr)) return false;

        return true;
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter an IF expression: ");
        String input = sc.nextLine();

        if (isValidIf(input)) {
            System.out.println("Valid IF Expression");
        } else {
            System.out.println("Invalid IF Expression");
        }

        sc.close();
    }
}
