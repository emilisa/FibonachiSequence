FibonachiSequence
=================
using System;

using System.Collections.Generic;

class FibonachiSequence

{

    static void Main()

    {
        try
        {
            Console.Title = "FibonachiSequence";
            Console.BufferWidth = 120;

            List<decimal> fibonachiSequence = new List<decimal> { 1 };

            Console.WriteLine("To witch member of Fibonachi sequence you want to print:");
            
            // Показва до кой член ще се изпечати редицата на фибоначи.

            int fibonachiNumber = int.Parse(Console.ReadLine()); 

            decimal oldNumber = 0;
            decimal newNumber = 1;

            for (int i = 0; i < fibonachiNumber - 1; i++)
            {
                newNumber = newNumber + oldNumber;

                oldNumber = newNumber - oldNumber;

                fibonachiSequence.Add(newNumber);
            }

            Console.ForegroundColor = ConsoleColor.Yellow;
            Console.WriteLine("The first {0} members of Fibonachi sequence are", fibonachiNumber);
            Console.ResetColor();

            foreach (decimal item in fibonachiSequence)
            {
                Console.WriteLine("{0}", item);
            }

            Console.ReadKey();
        }

        catch (Exception e)
        {
            Console.WriteLine("EITHER sequence is too large - Max members is 139");
            Console.WriteLine("OR char is typed - Please type number");
            Console.ReadKey();
        }
    }
}
