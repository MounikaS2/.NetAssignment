# .NetAssignment
using System;
class Program
{
    static void Main()
    {
        Console.Write("Enter the height of the triangle: ");
        int height = int.Parse(Console.ReadLine());

        PrintTriangle(height);
    }

    static void PrintTriangle(int height)
    {
        for (int i = 1; i <= height; i++)
        {
            // Print spaces before each line
            for (int j = 0; j < height - i; j++)
            {
                Console.Write(" ");
            }

            // Print stars for each line
            for (int k = 0; k < 2 * i - 1; k++)
            {
                Console.Write("*");
            }

            // Move to the next line
            Console.WriteLine();
        }
    }
}
