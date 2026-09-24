# Mark-1
using System;

public class CourseResult
{
    public string StudentName { get; set; }
    private double mark;

    public double Mark
    {
        get
        {
            return mark;
        }
        set
        {
            if (value >= 0 && value <= 100)
            {
                mark = value;
            }
            else
            {
                Console.WriteLine("not ");
            }
        }
    }

    public char Grade
    {
        get{
            if (mark >= 90) return 'A';
            if (mark >= 80) return 'B';
            if (mark >= 70) return 'C';
            if (mark >= 50) return 'D'; 
            return 'F';
        }
    }

    public bool Passed
    {
        get
        {
            return mark >= 50;
        }
    }

    public void PrintResult()
    {
        Console.WriteLine($"Student Name: {StudentName}");
        Console.WriteLine($"Mark: {mark}");
        Console.WriteLine($"Grade: {Grade}");
        Console.WriteLine($"Result: {(Passed ? "Pass" : "Fail")}");
    }
}

class Program
{
    static void Main()
    {
        CourseResult cour = new CourseResult();

        Console.Write("Enter the name: ");
        cour.StudentName = Console.ReadLine();

        Console.Write("Enter the mark: ");
        cour.Mark = Convert.ToDouble(Console.ReadLine());

        Console.WriteLine("\n--- First Result ---");
        cour.PrintResult();

        Console.WriteLine("\n--- Testing Valid Mark (85) ---");
        cour.Mark = 85;
        cour.PrintResult();

        Console.WriteLine("\n--- Testing Invalid Mark (150) ---");
        cour.Mark = 150;
      
    }
}
