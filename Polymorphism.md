Polymorphism is the ability of an object to take on many forms. The most common use of polymorphism in OOP
occurs when a parent class reference is used to refer to a child class object.

Any Java object that can pass more than one Is-A test is considered to be polymorphic. In Java, all Java objects
are polymorphic since any object will pass an is-A test for their own type and for the class object.

It is important to know that the only way to access an object is through a reference variable. A reference variable
can be of only one type. Once declared, the type of a reference variable cannot be changed.

The reference variable can be reassigned to other objects provided it is not declared final. The type of reference
variable would determine the methods that it can invoke on the object.

A reference variable can refer to any object of its declared type. A reference variable can be declared as a class
or interface type.

                     public interface Vegetarian{}
                     public class Animal{}
                     public class Deer extends public class Animal implements Vegetarian{}
                     
Now, the Deer class is considered to be polymorphic since it has multiple inheritance. Following are true
for the above example:

- A Deer is-A animal
- A Deer is-A vegetarian
- A deer is-A deer
- A deer is-A Object

When we apply the reference variable facts to a Deer object reference, the following declarations are legal:

                      Deer d = new Deer();
                      Animal a = d;
                      Vegetarian v = d;
                      Object o = d;
                      
All the reference variables d, a , v, and o refer to the same d object in the heap.

<h2>Virtual Methods</h2>
In this section, I will show you how the behavior of overridden methods in Java allows you to take advantage of 
polymorphism when defining your classes.

We have already discussed method overriding, where a child class can override a method in its parent. An overridden
method is essentially hidden in the parent class, and is not invoked in the child class using the super keyword within the
override method.

                        public class Employee {
                         private String name;
                         private String address;
                         private int number;
                        
                         public Employee(String name, String address, int number) {
                          System.out.println("Constructing an employee");
                          this.name=name;
                          this.address=address;
                          this.number=number;
                          }
                        
                        public void mailCheck(){
                         System.out.println("Mailing a check to" + this.name + "" + this.address); }
                        
                        public String toString() {
                         return name + "" + address + "" + number;
                         }
                        }
                        
                        public String getName() {
                        return name;
                        }
                        
                        public String getAddress() {
                        return address;
                        }
                        
                        public void setAddress(String newAddress) {
                         address = newAddress;
                        }
                        
                        public intNumber(){
                         return number;
                          }
                         }
                         
  Now, we extend the Employee class as follows:
  
                         public class Salary extends Employee {
                          private double salary; //Annual Salary
                          public Salary(String name, String address, int number, double salary) {
                           super(name, address, number);
                           setSalary(salary);
                           }
                          public void mailCheck()
                          {
                          System.out.println("Within mailcheck of salary check");
                          System.out.println("Mailing check to" + getName() + "with salary" +salary);
                          }
                          public double getSalary(){
                          return salary;
                          }
                          public void setSalary(double newSalary){
                          if(newSalary>=0.0){
                          salary=newSalary;
                           }
                          }
                          double computePay() {
                          System.out.println("Computing salary pay for" + getName());
                          return salary/52;
                            }
                          }
                          
