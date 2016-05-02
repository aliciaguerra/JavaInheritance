# Java Inheritance

Inheritance can be defined as a process where one class acquires the properties (methods and fields of another).
With the use of inheritnce, the information is made managable in a hierarchal order.

The class which inherits the properties of another is known as a subclass (derived class, child class) and the class whose properties are inherited is known as the superclass (base class, parent class).

<h2>extends Keyword</h2>

extends is the keyword used to inherit the properties of a class.

    class Super {
      ...
      }
      
    class Sub Extends Super {
     ...
     }
     
Below given is an example dealing with Java inheritance. In this example you can observe two classes namely Calculation
and My_Calculation.

    class Calculation {
      int z;
      
      public void addition(int x, int y) {
       z=x+y;
       System.out.println("The sum of the given numbers" + z);
       }
       
      public void Substraction(int x, int y) {
       z=x-y;
       System.out.println("The difference between the given numbers" + z);
         }
        }
        
      public class My_Calculation extends Calculation {
        public void multiplication(int x, int y) {
         z=x*y;
         System.out.println("The product of the given numbers" + z);
         }
         
        public static void main(String args[]) {
         int a=20, b=10;
         My_Calculation demo = new My_Calculation();
         demo.addition(a,b);
         demo.Substraction(a,b);
         demo.multiplication(a,b);
          }
         }
         
In the given program when an object to My_Calculation class is created, a copy of the contents of the super class
is made within it. That is why, using the object of the subclass you can access the members of the superclass.

The superclass reference variable can hold the superclass object, but using the variable you can access only the members
of the superclass, so to access the members of both classes it is recommended to always create a reference variable to
subclass.

If you consider the above program you can instantiate the class as given below as well. But using the superclass
reference variable (cal in this case)


