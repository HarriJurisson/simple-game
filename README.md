using System;

class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Welcome to the Guessing Game!");
        Console.WriteLine("I'm thinking of a number between 1 and 100. Can you guess it?");

        Random random = new Random();
        int secretNumber = random.Next(1, 101);
        int attempts = 0;
        bool guessedCorrectly = false;

        while (!guessedCorrectly)
        {
            Console.Write("Enter your guess: ");
            string input = Console.ReadLine();
            if (!int.TryParse(input, out int guess))
            {
                Console.WriteLine("Please enter a valid number.");
                continue;
            }

            attempts++;

            if (guess < secretNumber)
            {
                Console.WriteLine("Too low! Try again.");
            }
            else if (guess > secretNumber)
            {
                Console.WriteLine("Too high! Try again.");
            }
            else
            {
                guessedCorrectly = true;
                Console.WriteLine($"Congratulations! You guessed the number {secretNumber} correctly in {attempts} attempts.");
            }
        }

        Console.WriteLine("Thanks for playing!");
    }
}
