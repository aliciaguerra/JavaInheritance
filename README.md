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
reference variable (cal in this case) you cannot call the method multiplication() , which belongs to the superclass
My_Calculation.

        Calculation cal = new My_Calculation();
        demo.addition(a,b);
        demo.Substraction(a,b);
        
A subclass inherits all the members (fields, methods, and nested classes) from its superclass. Constructors
are not members, so they are not inherited by subclasses, but the constructor of the superclass can be invoked
from the subclass.

<h2>super class</h2>
The super keyword is similar to the this keyword following are the scenarios where the super keyword is used.

It is used to differentiate the members of superclass from the members of the subclass, if they have same names.

It is used to invoke the superclass constructor from subclass.

<h2>Differentiating the Members</h2>
If a class is inheriting the properties of another class. And if the members of the superclass have the names
same as the subclass, to differentiate these variables we use the super keyword shown below:

        super.variable
        super.method();
        
The section provides you a program that demonstrates the usage of the super keyword.

In the given program you have two classes namely Sub_class and Super_class, both have a method named display() with
different implementations, and a variable named num with different values. We are invoking display() method of both
classes and printing the value of the variable num of both parents, 
        


