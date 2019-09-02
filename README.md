# NumberGuesser
using System;


namespace projeto2
{
    class Program
    {
        static void Main(string[] args)
        {

            GetAppInfo();

            GreetUser();

            while (true)
            {

                //Static Init correct number
                //int correctNumber = 3;

                //Create a new Random Object
                Random random = new Random();

                //Dynamic Init correct number
                int correctNumber = random.Next(1, 10);


                //Init guess var
                int guess = 0;

                //Ask for a Number
                Console.WriteLine("Guess a number between 1 and 10");

                //While guess is not correct 
                while (guess != correctNumber)
                {
                    //get users input
                    string input = Console.ReadLine();

                    if (!int.TryParse(input, out guess))
                    {

                        //Print error messagem
                        PrintColorMessage(ConsoleColor.Yellow, "Please enter an actual number");
                       
                        
                        //Keep going
                        continue;

                    }

                    //cast to int and put in guess
                    guess = Int32.Parse(input);

                    //Match guess to correct number
                    if (guess != correctNumber)
                    {

                        //Tell user its the wrong number
                        PrintColorMessage(ConsoleColor.DarkRed, "Wrong Number >_< Please try again");

                                               
                    }
                }

                
                //Tell user its the right number
                PrintColorMessage(ConsoleColor.Magenta, "You are correct -_-");

                

                //Ask to play again 
                Console.WriteLine("Play again? [Y or N]");

                //Get answer
                string answer = Console.ReadLine().ToUpper();

                if (answer == "Y")
                {
                    continue;
                }

                else if (answer == "N")
                {
                    return;
                }

                else
                {
                    return;
                }

            }


            }

            static void GetAppInfo()
            {
                //set app vars
                string appName = "Number Guesser";
                string appVersion = "1.0.0";
                string appAuthor = "Stefhanie Hecke Melo";

                //Change text Color
                Console.ForegroundColor = ConsoleColor.Cyan;

                //Write out app info
                Console.WriteLine("{0}: Version {1} by {2}", appName, appVersion, appAuthor);

                //Reset text color
                Console.ResetColor();

            }

            static void GreetUser()
            {
                //Ask user name
                Console.WriteLine("What´s your name?");

                //Get user input
                string inputName = Console.ReadLine();

                Console.WriteLine("Hey {0}, What´s up? Let´s play a game...", inputName);
            }
        static void PrintColorMessage(ConsoleColor color, string message)
        {

            //Change text color
            Console.ForegroundColor = color;

            //Tell user the message 
            Console.WriteLine(message);

            //Reset text color
            Console.ResetColor();

        }
        
    }

}
