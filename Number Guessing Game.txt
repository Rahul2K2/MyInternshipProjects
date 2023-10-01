import java.util.Random;
import java.util.Scanner;

public class guessing {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        Random rand= new Random();

        int min = 1;
        int max = 100;
        int sn = rand.nextInt(max - min + 1) + min;
        int at = 0;
        boolean hasGuessedCorrectly = false;

        System.out.println("Welcome to the Number Guessing Game!");
        System.out.println("I've selected a number between " + min + " and " + max + ". Try to guess it.");

        while (!hasGuessedCorrectly) {
            System.out.print("Enter your guess: ");
            int userGuess = scan.nextInt();
            at++;

            if (userGuess < min || userGuess > max) {
                System.out.println("Please enter a number between " + min + " and " + max + ".");
            } else if (userGuess < sn) {
                System.out.println("Too low! Try again.");
            } else if (userGuess > sn) {
                System.out.println("Too high! Try again.");
            } else {
                System.out.println("Congratulations! You've guessed the number " + sn+ " correctly in " + at + " attempts.");
                hasGuessedCorrectly = true;
            }
        }

        scan.close();
    }
}