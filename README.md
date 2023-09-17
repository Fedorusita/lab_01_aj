# Task 1
```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;




namespace Lessons
{

    class Program
    {

        static void Main(string[] args)
        {
            string msg = "Type {0,8} |\t.NET {1,8} |\tSize = {2} \t| MIN = {3,30}\t| MAX = {4}";

            Console.Title = "Data types C#";

            Console.WriteLine("\n\t\t\t\t\tINTEGER TYPES: \n");

            Console.WriteLine(string.Format(msg, "byte", typeof(byte).Name, sizeof(byte), byte.MinValue, byte.MaxValue));

            Console.WriteLine(string.Format(msg, "sbyte", typeof(sbyte).Name, sizeof(sbyte), sbyte.MinValue, sbyte.MaxValue));

            Console.WriteLine(string.Format(msg, "short", typeof(short).Name, sizeof(short), short.MinValue, short.MaxValue));

            Console.WriteLine(string.Format(msg, "ushort", typeof(ushort).Name, sizeof(ushort), ushort.MinValue, ushort.MaxValue));

            Console.WriteLine(string.Format(msg, "int", typeof(int).Name, sizeof(int), int.MinValue, int.MaxValue));

            Console.WriteLine(string.Format(msg, "uint", typeof(uint).Name, sizeof(uint), uint.MinValue, uint.MaxValue));

            Console.WriteLine(string.Format(msg, "long", typeof(long).Name, sizeof(long), long.MinValue, long.MaxValue));

            Console.WriteLine(string.Format(msg, "ulong", typeof(ulong).Name, sizeof(ulong), ulong.MinValue, ulong.MaxValue));



            Console.WriteLine("\n\t\t\t\t\tFLOAT TYPES: \n");

            Console.WriteLine(string.Format(msg, "float", typeof(float).Name, sizeof(float), float.MinValue, float.MaxValue));

            Console.WriteLine(string.Format(msg, "double", typeof(double).Name, sizeof(double), double.MinValue, double.MaxValue));

            Console.WriteLine(string.Format(msg, "decimal", typeof(decimal).Name, sizeof(decimal), decimal.MinValue, decimal.MaxValue));



            Console.WriteLine("\n\t\t\t\t\tSYMBOL TYPES: \n");

            Console.WriteLine(string.Format(msg, "Char", typeof(Char).Name, sizeof(Char), Char.MinValue, Char.MaxValue));

            Console.WriteLine(string.Format(msg, "string", typeof(string).Name, "N/A", "N/A", "N/A"));



            Console.WriteLine("\n\t\t\t\t\tLOGIC TYP: \n");

            Console.WriteLine(string.Format(msg, "bool", typeof(bool).Name, sizeof(bool), bool.FalseString, bool.TrueString));




            Console.WriteLine("\n\t\t\t\t\tSPECIAL TYPES: \n");

            Console.WriteLine(string.Format(msg, "object", typeof(Object).Name, "N/A", "N/A", "N/A"));

            Console.WriteLine(string.Format(msg, "dynamic", "N/A", "N/A", "N/A", "N/A"));

            Console.ReadKey();

        }
    }
}
```
![image](https://github.com/Fedorusita/lab_01_aj/assets/112895410/9188114c-2a72-4d2c-9961-40a9b35d3abe)


# Task 2   

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
# Task 3   
```
using System;

class Point                         
{
    private int x;
    private int y;

    public int X                   
    {
        get { return x; }
    }

    public int Y
    {
        get { return y; }
    }

    public Point(int x, int y)      
    {
        this.x = x;                 
        this.y = y;
    }
}

class Figure                        
{
    private Point[] points;
    private string name;

    public Figure(Point p1, Point p2, Point p3, Point p4) 
    {                                                                      
        points = new Point[4];
        points[0] = p1;
        points[1] = p2;
        points[2] = p3;
        points[3] = p4;
    }

    public string Name
    {
        get { return name; }
        set { name = value; }
    }

    public double LengthSide(Point A, Point B)
    {
        int dx = A.X - B.X;
        int dy = A.Y - B.Y;
        return Math.Sqrt(dx * dx + dy * dy);
    }

    public void PerimeterCalculator()
    {
        double perimeter = 0;
        for (int i = 0; i < points.Length - 1; i++)
        {
            perimeter += LengthSide(points[i], points[i + 1]);
        }

        if (points.Length > 2)
        {
            perimeter += LengthSide(points[points.Length - 1], points[0]);
        }

        Console.WriteLine($"Название фигуры: {name}");
        Console.WriteLine($"Периметр: {perimeter}");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Point p1 = new Point(0, 0);
        Point p2 = new Point(0, 5);
        Point p3 = new Point(5, 5);
        Point p4 = new Point(5, 0);

        Figure rectangle = new Figure(p1, p2, p3, p4);  
        rectangle.Name = "Прямоугольник";  
        rectangle.PerimeterCalculator();   
    }
}

<img width="595" alt="image" src="https://github.com/Fedorusita/lab_01_aj/assets/112895410/c7f188b5-697a-46b7-a1f1-cdbb754ee4ab">

