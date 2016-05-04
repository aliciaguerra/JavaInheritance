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
classes and printing the value of the variable num of both classes, here you can observe that we have used super
key word to differentiate the members of super class from sub class.

     class Super_class {
      int num=20;
      //display method of superclass
      public void display() {
       System.out.println("This is the display method of superclass");
       }
      }
      
      public class Sub_class extends Super_class {
       int num = 10;
       
       //display method of sub class
       public void display() {
        System.out.println("This is the display method of subclass");
        }
        
       public void my_method() {
        //Instantiating subclass
        Sub_class sub = new Sub_class();
        
        //Invoking the display() method of subclass
        sub.display();
        
        //Invoking the display() method of the superclass
        super.display();
        
        //printing the value of variable num of a subclass
        System.out.println("value of the variable named num in subclass"+sub.num);
        
        //printing the value of variable num of a superclass
        System.out.println("value of the variable named num is super class"+super.num);
        }
        
        public static void main(String args[]) {
         Sub_class obj = new Sub_class();
         obj.my_method();
             }
        }
        
<h2>Invoking Superclass constructor</h2>
If a class is inheriting the properties of another class, the subclass automatically requires the
default constructor of the super class. But if you want to call a parameterized constructor of 
the super class, you need to use the super keyword as shown below:
           
            super(values);
            
The program in this section demonstrates how to use the super keyword to invoke the parameterized constructor
of the super class. This program contains a super class and a sub class, where the super class contains a
parameterized constructor which accepts a string value, and we used the super keyword to invoke the parameterized
consturctor of the super class.

        class Superclass {
         int age;
         
         Superclass(int age) {
          this.age=age;
          }
          
          public void getAge(){
           System.out.println("The value of the variable named age in superclass is" + age);
           }
          }
          
          public class Subclass extends Superclass {
           Subclass(int age) {
            super(age);
            }
            
          public static void main(String args[]) {
            Subclass s = new Subclass(24);
            s.getAge();
            }
        }
        
<h2>Is-A Relationship</h2>
Is-A is a way of saying: this object is a type of object. Let us see how the extends keyword is used to 
achieve inheritance.

        public class Animal {
         }
        
        public class Mammal extends Animal {
        }
        
        public class Reptile extends Animal {
        }
        
        public class Dog extends Mammal {
        }
    
    Now, based on the above example, in object oriented terms, the following are true:
     - animal is the superclass of Reptile class
     - animal is the superclass of Reptile class
     - mammal and reptile are subclasses of Animal class
     -dog is the subclass of both Mammal and Animal classes
     
    Now if we consider an is-A relationship, we can say
     -Mammal is-A Animal
     -Reptile is-A Animal
     -Dog is-A Mammal
     -Hence, dog is-A mammal as well
     
With the use of extends keyword the subclasses will be able to inherit all the properties of the superclass
except for the private properties of the superclass.
We can assure that Mammal is actually an Animal with the use of the instance operator.

<h2>Example</h2>

         class Animal {
          }
         class Mammal extends Animal {
         }
         public class Dog extends Mammal {
          public static void main(String args[]){
           Animal a = new Animal();
           Mammal m = new Mammal();
           Dog d = new Dog();
           System.out.println(m instanceof Animal);
           System.out.println();
           }
          }
  
  This will produce the following result.
  
         true
         true
         true
    
   Since we have a good understanding of the extends keyword, let us look at how the implements keyword is used
   to get the Is-A relationship. Generally, the implements keyword is used with classes to inherit the properties 
   of an interface. Interfaces can never be extended by a class.
   
   <h2>Example</h2>
   
                  public interface Animal {
                   }
                   
                  
        


