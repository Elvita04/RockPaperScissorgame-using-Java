# RockPaperScissorgame-using-Java
import java.util.Random;
import java.util.Scanner;

public class RockPaperScissors {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        String[] choices = {"rock", "paper", "scissors"};
        
        System.out.println("Welcome to Rock, Paper, Scissors!");
        
        while (true) {
            // Get user input
            System.out.print("Enter your choice (rock, paper, or scissors). Type 'exit' to quit: ");
            String userChoice = scanner.nextLine().toLowerCase();

            // Exit condition
            if (userChoice.equals("exit")) {
                System.out.println("Thanks for playing!");
                break;
            }

            // Validate user input
            if (!userChoice.equals("rock") && !userChoice.equals("paper") && !userChoice.equals("scissors")) {
                System.out.println("Invalid choice. Please choose rock, paper, or scissors.");
                continue;
            }

            // Generate computer choice
            int compChoiceIndex = random.nextInt(3);
            String compChoice = choices[compChoiceIndex];
            
            System.out.println("Computer chose: " + compChoice);
            
            // Determine the winner
            if (userChoice.equals(compChoice)) {
                System.out.println("It's a tie!");
            } else if ((userChoice.equals("rock") && compChoice.equals("scissors")) ||
                       (userChoice.equals("paper") && compChoice.equals("rock")) ||
                       (userChoice.equals("scissors") && compChoice.equals("paper"))) {
                System.out.println("You win!");
            } else {
                System.out.println("Computer wins!");
            }
        }
        
        scanner.close();
    }
}
