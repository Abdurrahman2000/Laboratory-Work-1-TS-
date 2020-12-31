# Laboratory-Work-1-TS- Code for Taylor series calculation of exponential (-x) 
#include <stdio.h>
#include <math.h>


int expon (int b)
{
   int n, f, c;
   long double fir,put,sum; //fir- first term/next term,put-penultimate term,sum-tayylor series sum
   float dif;
   fir=pow(-1,n)*pow(b,n)/1;
   sum=fir;
   for (dif=1,n = 1;n<=1000 ; n++) //loop for n=1 to n=1000
    {put=fir;
      fir = fir*(-1)*b/n;
      sum = sum + fir;
      dif=sum-exp(-b);
      if (dif<0)
      dif=-dif;
      if (dif<=3e-6){    //minimum difference between real exp value and talor series value
          printf("Penultimate term = %Lf\n",put);
          printf("Last term = %Lf\n",fir);
          printf ("Value through taylor series = %Lf\n", sum);
          printf("Difference between e^(-%d) and Taylor series value = %f \n",b,dif);
          return 0;
      }
       }
}

int
main ()
{
  int a, d;
   printf ("Enter a value for e^-x calculation \n");
 scanf ("%d", &a);
  printf ("Exponential real value e^-%d = %f \n", a, exp (-a));
   expon(a);
   return 0;
}
