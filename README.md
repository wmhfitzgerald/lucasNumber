# lucasNumber

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Lucas {
    class Program
    {
        static int LucasNumber(int n) {
            
            int a = 2;
            int b = 1;
            
            for (int i = 1; i < n; i++)
            {
                int temp = a;
                a = b;
                b = temp + b;
            }
            
            return a;
            
        }
        
        static void Validate(int input, int expected)  {
            int actual = LucasNumber(input);
            
            Console.WriteLine(string.Format("{0} -> {1}", input, actual));
            
            if(actual != expected) {
               throw new ApplicationException(string.Format("Expected {0}"));
            }
        }

        static int Main(string [] args) {
            Validate(1,2);
            Validate(2,1);
            Validate(3,3);
            Validate(5,7);
            Validate(8,29);
            Validate(11,123);
            Validate(15,843);
            Console.WriteLine("Success! You can calculate Lucas Numbers!");
            return 0;
        }
    }
}
