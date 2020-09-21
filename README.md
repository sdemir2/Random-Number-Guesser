
/**
 * Programmer: Samet Demir
 * Class: CMSC203-25800
 * Description: 
 * This is a number guessing game. Simply, the program 
 * asks you to enter a number, and it tells you weather 
 * your number is the chosen random number or not. 
 * If not, you continue until getting it right. 
 * At the end, maybe you finished the game in 4th
 * or 7th, the program ends.
 */

import java.util.Random;
import java.util.Scanner;

@SuppressWarnings("unused")
public class RandomNumberGuesser {

	public static void main(String[] args) {
		guessingGame();

	}

	public static void guessingGame() {

		// Variables
		int nextGuess;
		int numGuesses = 1;
		int lowGuess = 0;
		int highGuess = 100;
		String yesno;
		@SuppressWarnings("unused")
		boolean win;

		// Constant variables
		final String PROGRAMMER_NAME = "Samet Demir";
		final String CLASS_NAME = "CMSC203-25800";

		// Picking a random number
		int 	randNum = (int) (Math.random() * 
				(highGuess - lowGuess + 1) + lowGuess);

		// Welcome message for the user
		System.out.println("Hi! Welcome to Samet's "+
							"Number guessing game");
		System.out.println("---------------------"+
							"-----------------------");
		System.out.println("Enter your first guess");

		// The repetition begins here
		do {

			@SuppressWarnings("resource")
			Scanner keyboard = new Scanner(System.in);
			nextGuess = keyboard.nextInt();

			System.out.println("Number of guesses is " + numGuesses);
			numGuesses++; // Incrementing

			// If the user gets his/her guess right, congratulate
			if (nextGuess == randNum) {
				win = true;
				System.out.println("\nCongratulations, you guessed" + 
				" correctly" + "\nTry again? (yes or no)");
				@SuppressWarnings("resource")
				Scanner endprogram = new Scanner(System.in);
				yesno = endprogram.nextLine();

				// If the user doesn't want to play more, end the program
				if (yesno.equals("n") || yesno.equals("N") || 
						yesno.equals("no") || yesno.equals("NO")) {
					System.out.println("Thanks for playing...");

					System.out.println("\nProgrammer: " + PROGRAMMER_NAME 
							+ "\nClass: " + CLASS_NAME);
					System.exit(0);

				} else {
					System.out.println("Enter your first guess");
				}
				;
			}

			// If the number isn't guessed right, help user find the answer
			else {

				if (nextGuess > randNum) {
					System.out.println("Your guess is too high");
					System.out.println("Please enter your next guess "+
										"between 0 and " + nextGuess);
				}
				// Guessed number is smaller than random number
				else if (nextGuess < randNum) {
					System.out.println("Your guess is too low");
					System.out.println("Please enter your next guess between "
										+ nextGuess + " and " + highGuess);
					// Guessed number is
				} else {

				}
			}
		}

		while (win = true);

	}
}
