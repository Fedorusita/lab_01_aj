# Task 1

```
using System;

namespace lab_01
{
    class Rectangle
    {
        private double side_1;
        private double side_2;

        public Rectangle(double sideA, double sideB)
        {
            side_1 = sideA ;
            side_2 = sideB;
        }
        private double CalculateArea()
        {
            return (side_1 * side_2);
        }
        double CalculatePerimeter()
        {
            return (2 * (side_1 + side_2));
        }
        public double Area
        {
            get { return CalculateArea(); }
        }
        public double Perimeter
        {
            get { return CalculatePerimeter(); }
        }

    }
    class Program   
    {
        static void Main()
        {
            Console.WriteLine("Введите длину первой стороны прямоугольника:");
            double sideA = double.Parse(Console.ReadLine());                  //parse - конвертация из строки в double

           
            Console.WriteLine("Введите длину второй стороны прямоугольника:");
            double sideB = double.Parse(Console.ReadLine());

            Rectangle rectangle = new Rectangle(sideA, sideB);

            Console.WriteLine($"Площадь прямоугольника: {rectangle.Area}");
            Console.WriteLine($"Периметр прямоугольника: {rectangle.Perimeter}");

            Console.ReadKey();
        }
    }
    
}
```
