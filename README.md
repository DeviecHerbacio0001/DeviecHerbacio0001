using System.Windows.Forms;

namespace MayorDeTresNumeros
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Ingrese tres números enteros diferentes: 49, 36 y 53");

            int numero1, numero2, numero3;

            // Leer el primer número
            Console.Write("Primer número: ");
            numero1 = Convert.ToInt32(Console.ReadLine());

            // Leer el segundo número
            Console.Write("Segundo número: ");
            numero2 = Convert.ToInt32(Console.ReadLine());

            // Leer el tercer número
            Console.Write("Tercer número: ");
            numero3 = Convert.ToInt32(Console.ReadLine());

            // Verificar si los números son diferentes y están dentro de las restricciones
            if (SonDiferentes(numero1, numero2, numero3) && SonValidos(numero1, numero2, numero3))
            {
                // Encontrar el mayor número
                int mayor = numero1;

                if (numero2 > mayor)
                {
                    mayor = numero2;
                }

                if (numero3 > mayor)
                {
                    mayor = numero3;
                }

                Console.WriteLine($"El mayor de los tres números es: {mayor}");
            }
            else
            {
                Console.WriteLine("Los números ingresados no cumplen con las restricciones.");
            }
        }

        static bool SonDiferentes(int a, int b, int c)
        {
            return a != b && a != c && b != c;
        }

        static bool SonValidos(int a, int b, int c)
        {
            int[] numerosValidos = { 49, 36, 53 };
            return Array.IndexOf(numerosValidos, a) != -1 && Array.IndexOf(numerosValidos, b) != -1 && Array.IndexOf(numerosValidos, c) != -1;
        }
    }
}
