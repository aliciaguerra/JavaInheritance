In the previous chapter, we talked about super classes and sub classes. If a class inherits a method from its superclass,
then there is a chance to override the method provided it is not marked final. 

The benefit of overriding is: abilitiy to determine a behavior that's specific to the subclass type which means a subclass 
can implement a parent class method based on its requirement.

In object-oriented terms, overriding means to override the functionality of an existing method.

<h2>Example</h2>

                     class Animal{
                       public void move(){
                       System.out.println("Animals can move");
                          }
                        }
                        
                     class Dog extends Animal {
                        public void move(){
                        System.out.println("Dogs can walk and run");
                        }
                      }
                      
                      public class TestDog{
                      public static void main(String args[]){
                        Animal a=new Animal(); //Animal reference and object
                        Animal b=new Dog(); //Animal reference but Dog object
                        a.move(); //runs the method in Animal class
                        b.move(); //runs the method in Dog class
                         }
                        }
                        
 In the above example, you can see that even though b is a type of Animal, it runs the move method in the Dog method.
 The reason for this is: in compile time, the check is made on the reference type. However, in the runtime, JVM
 figures out the object type and would run the method that belongs to the particular object.
 
 Therefore, in the above example, the program will compile properly since Animal class in the method move. Then,
 at the runtime, it runs the method for that object.
 
                        class Animal {
                         public move(){
                         System.out.println("Animals can move");
                         }
                        }
                        
                        class Dog extends Animal{
                        public void move(){
                        System.out.println("Dogs can walk and run");
                        }
                        public void bark(){
                        System.out.println("Dogs can bark");
                         }
                        }
                        
                        public class TestDog {
                        public static void main(String args[]){
                        Animal a = new Animal();//Animal reference and object
                        Animal b = new Dog(); //Animal reference but dog object
                        
                        a.move();//runs the method in Animal class
                        b.move();//runs the method in Dog class
                        b.bark();
                           }
                          }
                          
  This program will throw a compile time error since b's reference type Animal doesn't have a method by bark.
  
  <h2>Rules of Overriding</h2>
  
  - The argument list should be exactly the same as that of the overriden method.
  - The return type should be the same or a subtype of the return type declared in the original overriden method
     in the superclass.
  - The access level cannot be more restricitive than the overriden method's access level. For example: if the superclass
     method is declared public then the overriding method cannot be either private or protected.
  - Instance methods can be overriden only if they are inherited by the subclass.
  - A method declared final cannot be overridden.
  - A method declared static cannot be overridden but can be re-declared.
  - If a method cannot be inherited, then it cannot be overridden.
  - As a subclass within the same package as the instance's superclass can override any superclass method that is not
    declared private or final.
  - A subclass in a different package can only override the non-final methods declared public or protected.
  - An overriding method can throw any uncheck exceptions, regardless of whether the overriden method throws exceptions
    or not. However, the overriding method should not throw checked exceptions that are new or broader than the ones 
    declared by the overriden method. The overriding method can throw narrower or fewer exceptions than the overriden 
    method.
  - Constructors cannot be overridden.
  
<h2>Using the super Keyword</h2>
When invoking a superclass version of an overridden method, the super method is used.

                    class Animal {
                      public void move() {
                       System.out.println("Animals can move"); 
                           }
                          }
                          
                    class Dog extends Animal {
                      public void move() {
                      super.move(); //invokes the super class method
                      System.out.println("Dogs can walk and run");
                      }
                    }
                    
                    public class TestDog {
                    public static void main(String args[]) {
                    Animal b=new Dog(); //Animal reference but dog object
                    b.move(); //runs the method in the dog class
                     }
                    }

