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
                      
