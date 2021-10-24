using System;

namespace ConsoleApp3
{
    class Program
    {
        static void Main(string[] args)
        {
           //2.1 Высокий уровень
            try
            {

                Console.WriteLine("введите x");
                double x = double.Parse(Console.ReadLine());
                Console.WriteLine("введите y");
                double y = double.Parse(Console.ReadLine());
                if (x <= 2 && y <= 2 && x >= 0 && y >= 0 && x + y >= 1 && x + y <= 3) Console.WriteLine("да");
                else Console.WriteLine("нет");
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
            //2.2. Начальный уровень
            try
            {
                Console.WriteLine("Введите A(x0;y0):");
                double x0 = double.Parse(Console.ReadLine());
                double y0 = double.Parse(Console.ReadLine());
                Console.WriteLine("Введите B(x1;y1):");
                double x1 = double.Parse(Console.ReadLine());
                double y1 = double.Parse(Console.ReadLine());
                if (x0 + y0 < x1 + y1) Console.WriteLine("Точка A(x0;y0) наименее удалена от начала кординат");
                else Console.WriteLine("Точка B(x1;y1) наименее удалена от начала кординат");
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }


            //2.3. Средний уровень
            try
            {
                Console.WriteLine("Введите 1,2 или 3");
                int n = int.Parse(Console.ReadLine());
                Console.Write("Введите x:");
                double x = double.Parse(Console.ReadLine());
                double a = 0, b = 0, c = 0, y = 0;
                switch (n)
                {
                    case 1: a = 3.5; b = -0.73; c = 2.5; break;
                    case 2: a = 15.4; b = -5.6; c = 3.5; break;
                    case 3: a = 5.1; b = 4; c = 2.7; break;
                }
                if (Math.Abs(1 - x * x) == a + c) y = Math.Sqrt(Math.Abs(a * x - Math.Cos(b * b * b * x) * Math.Cos(b * b * b * x) + 5.1 * c * c));
                else if (Math.Abs(1 - x * x) > a + c) y = Math.Exp(0.04 * x) + Math.Log(Math.Abs(b * b * b * b * b * Math.Cos(x)));
                else if (Math.Abs(1 - x * x) < a + c) y = Math.Cos(b * b * b * x * x) * Math.Cos(b * b * b * x * x) + Math.Log(Math.Abs(b * x - a * a));
                Console.WriteLine($"y={y:F2}");
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
