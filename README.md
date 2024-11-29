# komisia-29.11
Ремизов Иван Сергеевич 29.11.2024
Выполнение задания 
using System;

public class Calculator
{
    public double Add(double a, double b) => a + b;
    public double Divide(double a, double b)
    {
        if (b == 0)
            throw new DivideByZeroException("Cannot divide by zero.");
        return a / b;
    }
}

class Program
{
    static void Main(string[] args)
    {
        Calculator calculator = new Calculator();

        Console.WriteLine("Simple Calculator");
        Console.WriteLine("Enter the first number:");
        double num1 = double.Parse(Console.ReadLine());

        Console.WriteLine("Enter the operation (+, /):");
        string operation = Console.ReadLine();

        Console.WriteLine("Enter the second number:");
        double num2 = double.Parse(Console.ReadLine());

        try
        {
            double result = operation switch
            {
                "+" => calculator.Add(num1, num2),
                "/" => calculator.Divide(num1, num2),
                _ => throw new InvalidOperationException("Invalid operation.")
            };

            Console.WriteLine($"Result: {result}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"Error: {ex.Message}");
        }
    }
}
