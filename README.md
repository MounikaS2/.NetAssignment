# .NetAssignment1
1. Print triangle - and allow user to set height of it in. Like in the following case it’s 4.
*
***
*****
*******
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
 for (int k = 0; k < 2 * i - 1; k++
{
 Console.Write("*");
 }
// Move to the next line
 Console.WriteLine();
 }
 }
}


# .NetAssignment2
2. Find valid date (MMDDYYYY) from string.
For example :-
Hdjsh asd2324234jghjsd hjsdg sdhk 12212021 idf32432 32423 d34234jh dfh.
using System;
using System.Text.RegularExpressions;
class Program
{
 static void Main()
 {
 string input = "Hdjsh asd2324234jghjsd hjsdg sdhk 12212021 idf32432 32423 d34234jh dfh";
 string pattern = @"\b(\d{2})(\d{2})(\d{4})\b";
 MatchCollection matches = Regex.Matches(input, pattern);
 foreach (Match match in matches)
 {
 string month = match.Groups[1].Value;
 string day = match.Groups[2].Value;
 string year = match.Groups[3].Value;
 if (IsValidDate(int.Parse(month), int.Parse(day), int.Parse(year)))
 {
 string date = month + day + year;
 Console.WriteLine(date);
 }
 }
 }
 static bool IsValidDate(int month, int day, int year)
 {
 try
 {
 DateTime date = new DateTime(year, month, day);
 return true;
 }
 catch (ArgumentOutOfRangeException)
 {
 return false;
 }
 }
}
