import java.util.Random;
import java.util.Scanner;
public class NumberGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        int min = 1;
        int max = 100;
        int targetNumber = random.nextInt(max - min + 1) + min;
        int attempts = 0;
        boolean isCorrect = false;
        System.out.println("Welcome to the Number Game!");
        while (!isCorrect) {
            System.out.print("Enter your guess (between 1 and 100): ");
            int guess = scanner.nextInt();
            attempts++;

            if (guess == targetNumber) {
                System.out.println("Congratulations! Your guess is correct!");
                isCorrect = true;
            } else if (guess < targetNumber) {
                System.out.println("Too low! Try again.");
            } else {
                System.out.println("Too high! Try again.");
            }

            if (!isCorrect && attempts >= 5) {
                System.out.println("Oops! You've reached the maximum number of attempts.");
                break;
            }
        }

        System.out.println("Thank you for playing the Number Game!");
        System.out.println("Your score: " + attempts + " attempts.");
    }
}
