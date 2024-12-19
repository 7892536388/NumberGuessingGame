# NumberGuessingGame
import java.util.Random;
import java.util.Scanner;

public class NumberGuessingGame {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        
        System.out.println("Welcome to the Number Guessing Game!");
        System.out.print("Enter the number of rounds you want to play: ");
        int rounds = scanner.nextInt();
        int score = 0;

        for (int round = 1; round <= rounds; round++) {
            int numberToGuess = random.nextInt(100) + 1;  // Random number between 1 and 100
            int attempts = 5;
            boolean guessedCorrectly = false;

            System.out.println("\nRound " + round + ": Start guessing the number between 1 and 100.");
            
            while (attempts > 0) {
                System.out.print("Enter your guess: ");
                int userGuess = scanner.nextInt();
                attempts--;

                if (userGuess == numberToGuess) {
                    System.out.println("Congratulations! You guessed the correct number.");
                    guessedCorrectly = true;
                    score++;
                    break;
                }


   else if (userGuess < numberToGuess) {
                    System.out.println("Too low! Try again.");
                } else {
                    System.out.println("Too high! Try again.");
                }
                
                System.out.println("Attempts left: " + attempts);
            }

            if (!guessedCorrectly) {
                System.out.println("You've used all your attempts. The correct number was: " + numberToGuess);
            }
        }

        System.out.println("\nGame Over! You won " + score + " out of " + rounds + " rounds.");
        scanner.close();
    }
}
