An interface is a reference type in Java, it is similar to a class, it is a collection of abstract methods. A class
implements an interface, thereby inheriting the abstract methods of the interface.

Along with abstract methods, an interface may also contain constants, default methods, static methods, and nested types.
Method bodies exist only for default methods and static methods.

Writing an interface is similar to writing a class. But a class describes the behaviors and attributes of an object.
And an interface contains behaviors that a class implements.

Unless the class that implements the interface is abstract, all the methods of the interface need to be described in the
class.

An interface is similar to a class in the following ways:

- an interface can contain any number of methods
- an interface is written in a file with a .java extension with the name of the interface matching the name of the file
- the byte code of the interface appears in the .class file
- interfaces appear in packages, and their corresponding bytecode file must be in the directory structure that matches
  the package name
  
However, an interface is different from a class in several ways including:

- you cannot instantiate an interface
- an interface does not contain any constructors
- all of the methods in an interface are abstract
- an interface cannot contain instance fields. The only fields that can appear in an interface must be declared 
  static and final
- an interface is not extended by a class, it is implemented by a class
- a interface can extend mutilpe interfaces

<h2>Declaring Interfaces</h2>
The interface keyword is used to declare an interface. 

                            import java.lang.*;
                            public interface NameOfInstance{
                            //Any number of final,static fields
                            //any number of abstract method declarations
                            }
                            
  Interfaces have the following properties:
  - interfaces are implicitly abstract. You do not need to use the abstract keyword while declaring an interface.
  - Each method in an interface is also implicitly abstract, so the abstract keyword is not needed.
  - Methods in an interface are implictly public.
  
                              interface Animal {
                              public void eat();
                              public void travel();
                              }
  
  <h2>Implementing Interfaces</h2>
  When a class implements an interface, you can think of the class as signing a contract, agreeeing to perform the specific
  behaviors of the interface. If a class does not perform all the behaviors of the interface, the class must declare itself 
  abstract.
  
  A class uses the implements keyword to implement an interface. The implements keyword appears in the class declaration
  following the extends portion of the declaration.
  
                               public class MammalInt implements Animal{
                               public void eat(){
                               System.out.println("Mammal eats");
                               }
                               public void travel(){
                               System.out.println("Mammal travels");
                               }
                               public int noOfLegs(){
                               return 0;
                               }
                               public static void main(String args[]){
                               MammalInt m = new MammalInt();
                               m.eat();
                               m.travel();
                                }
                              }
                              
When overriding methods defined in interfaces, there are several rules to be followed:
- Checked exceptions should not be declared on implementation methods other than the ones declared by the interface
  methods or subclasses of those declared by the interface method.
- The signature of the interface method and the same return type or subtype should be maintained when overriding 
  the methods.
- An implementation class itself can be abstract and if so interface methods need not be implemented.

When implementing interfaces, there are several rules:
- a class can implement more than one interface at a time
- a class can only extend one class, but implement many interfaces
- an interface can extend another interface, similarly to the way a class extends another class

<h2>Extending Interfaces</h2>
An interface can extend another interface, similarly to the way a class can extend another class. The extends keyword is
used to extend an interface, and the child interface inherits the methods of the parent interface.

                                  public interface Sports {
                                    public void setHomeTeam(String name);
                                    public void setVisitingTeam(String name);
                                    }
                                  public interface FootBall extends Sports {
                                  public void homeTeamScored(int points);
                                  public void visitingTeamScored(int points);
                                  public void endOfQuarter(int quarter);
                                  }
                                  public interface Hockey extends Sports{
                                   public void homeGoalScored();
                                   public void visitingGoalScored();
                                   public void endOfPeriod(int period);
                                   public void overtimePeriod(int ot);
                                   }
                                   
  The hockey interface has four methods, but it inherits two from sports; thus, a class that implements Hockey needs
  to implement all six methods. Similarly, a class the implements FootBall needs to define the three methods from
  FootBall and the two methods from Sports.
  
  <h2>Extending Multiple Interfaces</h2>
  A Java class can only extend one parent class. Multiple inheritance is not allowed. Interfaces are not classes, 
  however, and an interface can extend more than one parent interface.
  
  The extends keyword is used once, and the parent interfaces are declared in a comma-separated list.
  
                                    public interface Hockey extends Sports, Events
                                    
  <h2>Tagging Interfaces</h2>
  The most important use of extending interfaces occurs when the parent interface does not extend any methods.
  For example, the mouseListener interface in the java.awt.Event package extended java.util.EventListener, which is
  defined as:
  
                             package java.util;
                             public interface EventListener{}
                             
  An interface with no methods in it is referred to as a tagging interface. There are two basic design purposes of
  tagging interfaces:
  - creates a common parent
   As with the EventListener interface, which is extended by dozens of other interfaces in the Java API, you can use a tagging
   interface to create a common interface among a group of interfaces. For example, when an interface extends EventListener,
   the JVM knows that this particular interface is going to be used in an event delegation scenario.
  -  adds a data type to the class
  This situation is where the term tagging comes from. A class that implements a tagging interface does not need to
  define any methods (since the interface does not have any), but the class becomes an interface type through polymorphism.
