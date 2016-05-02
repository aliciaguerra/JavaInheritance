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
        public void multiplication 

