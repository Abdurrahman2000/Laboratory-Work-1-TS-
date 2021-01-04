# Laboratory-Work-1-TS- Code for Taylor series calculation of exponential (-x) 
#include <stdio.h>
#include <math.h>


long double expon (int b)
{
   int n, f, c;
   long double fir,put, lat, sum;
   float dif;
   fir=pow(-1,n)*pow(b,n)/1;
   sum=fir;
   for (dif=1,n = 1;n<=1000 ; n++)
    {lat=put;
      fir = fir*(-1)*b/n;
      sum = sum + fir;
      dif=sum-exp(-b);
    put=fir;
      if (dif<0)
      dif=-dif;
      if (dif<=3e-6){
          printf("Penultimate term = %Lf\n",put);
          printf("Last term = %Lf\n",lat);
      return sum;}
       }
}

int
main ()
{
  printf("         1000\n");
  printf("        ------\n");
  printf("        .\n");
  printf("         .     (-1)^k.x^k            x^2    x^3\n");
  printf("e^(-x) =  .    ----------- = 1 - x + ---- + -----   .....  \n");
  printf("         .           k!               2!     3!  \n");
  printf("        .\n");
  printf("        ------\n");
  printf("          k=0\n");
  
  long double ex;
  int a, d;
   printf ("Enter a value for e^-x calculation \n");
 scanf ("%d", &a);
  printf ("Exponential real value e^-%d = %f \n", a, exp (-a));
   ex = expon (a);
   printf ("Value through taylor series = %Lf\n", ex);
   printf("Diference between real avlue and Taylor series sum : %Lf",exp(-a)-ex);
   return 0;
}
