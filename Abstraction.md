As per abstraction, Abstraction is the quality of dealing with ideas rather than events. For example, when you
consider the case of emails, complex details such as what happens when you send an email, the protocol your email
server uses are hidden from the user, therefore to send an email you just need to type the content, mention the address
of the reciever and press send.

Likewise, in OOP, abstraction is a process of hiding the implementation details from the user, only the functionality 
will be provided to the user. In other words user will have the information on what the object does instead of how 
it does it.

In Java abstraction is achieved using abstract classes and interfaces.

<h2>Abstract Class</h2>
A class which contains the abstract keyword in its declaration is known as an abstract class.

- Abstract classes may or may not contain abstract methods, i.e. methods without a body (public void get())
- But if a class has at least one abstract method, then the class must be declared abstract.
- If a class is declared abstract, it cannot be instantiated.
- To use an abstract class you have to inherit it from another class, provide implementations to the abstract methods
   in it.
- If you inherit an abstract class you have to provide implementations to all abstract methods in it.

<h2>Example</h2>
This section provides you with an example of the abstract class to create an abstract class just use the abstract keyword
before the class keyword in the class declaration.

                    public abstract class Employee {
                      private String name;
                      private String address;
                      private int number;
                      public Employee(String name, String address, int number) {
                        System.out.println("Constructing an employee");
                        this.name=name;
                        this.address=address;
                        this.number=number;
                        }
                      public double computePay(){
                        System.out.println("Inside employee computePay");
                        return 0.0;
                        }
                     public void mailCheck(){
                     System.out.println("Mailing a check to" + this.name + "" + this.address); }
                     public String toString(){
                     return name+""+address+number;
                     }
                     public String getName(){
                     return name;
                     }
                     public String getAddress(){
                     return address;
                     }
                     public void setAddress(String newAddress){
                     address=newAddress;
                     }
                     public int getNumber(){
                     return number;
                         }
                     }
                     
   You can observe that except abstract methods the Employee class is the same as a normal class in Java.
   The class is now abstract, but it still has three fields, seven methods, and one constructor.
   Now, you can try to instantiate the Employee class as shown below:
   
                     public class Abstract Demo(){
                      public static void main(String args[]) {
                       //Following is not allowed and would raise error
                       Employee e = new Employee("George W", "Houston, Texas", 43);
                       System.out.println("Call mailcheck using Employee reference");
                       e.mailCheck();
                       }
                       
   <h2>Inheriting the Abstract Class</h2>
   We can inherit the properties of the employee class just like the concrete class shown below.
                     
                      public class Salary extends Employee {
                      private double salary; //Annual Salary
                      public Salary(String name, String address, int number, double salary){
                      super(name, address, number);
                      setSalary(salary);
                      }
                      
                     public void mailCheck(){
                     System.out.println("Within mailcheck of salary class");
                     System.out.println("Mail check to" + getName() + "with salary" + salary);
                     }
                     
                     public double getSalary(){
                     return salary;
                     }
                     public void setSalary(double newSalary){
                     if(newSalary>=0.0){
                     salary=newSalary;
                      }
                     }
                     public double computePay(){
                     System.out.println("Computing salary pay for" + getName());
                     return salary/52;
                      }
                     }
                     
Here, you cannot instntiate the Employee class but you can instantiate the salary class, and using this instance 
you can access all three fields and seven methods of Employee shown below.

                     public class AbstractDemo {
                      public static void main(String args[]){
                       Salary s = new Salary("Mohd Motashim", "Ambetha, UP", 3, 3600.00);
                       Employee e = new Salary("John Adams", "Boston, MA", 2, 2400.00);
                       System.out.println("Call mailcheck using salary reference");
                       s.mailCheck();
                       System.out.println("Call mailcheck using Employee reference");
                       e.mailCheck();
                       }
<h2>Abstract methods</h2>
If you want a class to contain a particular method but you want the actual implementation of that to be determined by
the child classes, you declare the method in the parent class as abstract.

- abstract keyword is used to declare the method as abstract
- you have to place the abstract keyword before the method name in the method declaration
- an abstract method contains a method signature, but not method body
- instead of curly braces the abstract method will have a semicolon (;) at the end

                       public abstract class Employee{
                       private String name;
                       private String address;
                       
                       }
                      
                      
                        
                      
