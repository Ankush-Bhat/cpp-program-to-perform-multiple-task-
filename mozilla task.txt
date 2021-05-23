#include<iostream.h>
#include<conio.h>
#include<math.h>
void is_prime(int);
void is_square(int);
void is_cube(int);
int find_factorial(int);
void is_palindrome(int);
void is_neon(int);
void find_fibonacci(int);
void is_armstrong(int);
void is_disarium(int);
void is_harshad(int);
void main()
{
 clrscr();
 int number,choice;
 char answer;
 do
 {
  cout<<"MENU"<<endl;
  cout<<"1.Check for Prime Number"<<endl<<"2.Check for Square Number"<<endl<<"3.Check for Cube Number"<<endl<<"4.Find Factorial"<<endl<<"5.Check For Palindrome Number"<<endl<<"6.Check For Neon Number"<<endl<<"7.To find Fibonacci Series"<<endl<<"8.Check for Armstrong Number"<<endl<<"9.Check for Disarium Number"<<endl<<"10.Check For Harshad Number"<<endl;
  cout<<"Enter Your Choice(1-10):"<<endl;
  cin>>choice;
  cout<<"Enter a Number:"<<endl;
  cin>>number;
  switch(choice)
  {
   case 1:{
	   is_prime(number);
	   break;
	   }
   case 2:{
	   is_square(number);
	   break;
	   }
   case 3:{
	   is_cube(number);
	   break;
	   }
   case 4:{
	   int factorial=find_factorial(number);
	   cout<<number<<"!="<<factorial<<endl;
	   break;
	   }
   case 5:{
	   is_palindrome(number);
	   break;
	   }
   case 6:{
	   is_neon(number);
	   break;
	  }
   case 7:{
	   find_fibonacci(number);
	   break;
	   }
   case 8:{
	   is_armstrong(number);
	   break;
	   }
   case 9:{
	   is_disarium(number);
	   break;
	   }
   case 10:{
	    is_harshad(number);
	    break;
	    }
   default:{
	    cout<<"Invalid Choice!!!!"<<endl;
	    break;
	    }
  }
  cout<<"Do You Want To Continue(Y/N)"<<endl;
  cin>>answer;
  if((answer!='Y')||(answer!='y'))
  cout<<"Thank You ...... Visit Again......."<<endl;
  }while((answer=='y')||(answer=='Y'));
  getch();
}
void is_prime(int number)
{
 int i,prime=0;
 for(i=2;i<=number/2;++i)
 {
  if(number%i==0)
  {
   prime=1;
   break;
  }
 }
 if(prime==0)
 cout<<number<<"Is a Prime Number"<<endl;
 else
 cout<<number<<"Is Not a Prime Number"<<endl;
}
void is_square(int number)
{
 int integer_squareroot;
 float float_squareroot;
 float_squareroot=sqrt((double)number);
 integer_squareroot=float_squareroot;
 if(integer_squareroot==float_squareroot)
 cout<<number<<"is a Perfect Square"<<endl;
 else
 cout<<number<<"is not a perfect square"<<endl;
}
void is_cube(int number)
{
 int integer_cuberoot;
 float float_cuberoot;
 float_cuberoot=pow((double)number,1.0/3.0);
 integer_cuberoot=float_cuberoot;
 if(integer_cuberoot==float_cuberoot)
 cout<<number<<"is a Perfect Cube"<<endl;
 else
 cout<<number<<"is not a Perfect CubeS"<<endl;
}
int find_factorial(int number)
{
 if(number==0)
 return 0;
 else
 return(number*find_factorial(number-1));
}
void is_palindrome(int number)
{
 int store_number,reverse=0,reminder;
 store_number=number;
 while(number!=0)
 {
  reminder=number%10;
  number=number/10;
  reverse=(reverse*10)+reminder;
 }
 if(reverse==store_number)
 cout<<store_number<<"is a Palindrome Number"<<endl;
 else
 cout<<store_number<<"is not a PalindrSome Number"<<endl;
}
void is_neon(int number)
{
 int i,square,sum=0,reminder;
 square=number*number;
 while(square!=0)
 {
  reminder=square%10;
  sum+=reminder;
  square/=10;
 }
 if(sum==number)
 cout<<number<<"is Neon Number"<<endl;
 else
 cout<<number<<"is not a Neon Number"<<endl;
}
void find_fibonacci(int number)
{
 int Istterm=0,IIndterm=1,nextterm=0;
 cout<<"Fibonacci Series:"<<Istterm<<","<<IIndterm<<",";
 nextterm=Istterm+IIndterm;
 while(nextterm<=number)
 {
  cout<<nextterm<<",";
  Istterm=IIndterm;
  IIndterm=nextterm;
  nextterm=Istterm+IIndterm;
 }
 cout<<endl;
}
void is_armstrong(int number)
{
  int i,store_number,sum=0,reminder;
  store_number=number;
  while(number!=0)
  {
   reminder=number%10;
   sum=sum+pow(reminder,3);
   number=number/10;
  }
 if(sum==store_number)
 cout<<number<<"is Armstrong Number"<<endl;
 else
 cout<<number<<"is not an Armstrong Number"<<endl;
}
void is_disarium(int number)
{
 int reminder,store_number=number,power=0,sum=0;
 while(store_number!=0)
 {
  store_number/=10;
  power++;
 }
 store_number=number;
 while(store_number!=0)
 {
  reminder=store_number%10;
  sum+=pow(reminder,power);
  store_number/=10;
  power--;
 }
 if(sum==number)
 cout<<number<<"is a Disarium Number"<<endl;
 else
 cout<<number<<"is not a Disarium Number"<<endl;
}
void is_harshad(int number)
{
 int reminder,sum=0,store_number=number;
 while(number>0)
 {
  reminder=number%10;
  sum=sum+reminder;
  number=number/10;
 }
 if(store_number%sum==0)
 cout<<number<<"is a Harshad Number"<<endl;
 else
 cout<<number<<"is not a Harshad Number"<<endl;
}
