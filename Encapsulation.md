Encapsulation is one of the 4 fundamental OOP concepts. The other three are inheritance, polymorphism, and abstraction.
Encapsulation in Java is a mechanism of wrapping the data (variables) and code acting on the data (methods) together 
as a single unit. In encapsulation, the variables of a class will be hidden from other classes and can be accessed
only through methods of a current class, therefore it is known as data hiding.

To achieve encapsulation in Java:
- declare the variables of the class as private
- provide public getter and setter methods to modify and view the variable values

                        public class EncapsTest {
                          private String name;
                          private String idNum;
                          private int age;
                          
                        public int getAge(){
                        return age;
                        }
                        
                        public String getName(){
                        return name;
                        }
                        
                        public String getIdNum(){
                        return idNum;
                        }
                        
                        public void setAge(int newAge){
                        age=newAge;
                        }
                        
                        public void setName(String newName){
                        name=newName;
                        }
                        
                        public void setIdName(String newId){
                        idNum=newId;
                           }
                        }
                        
  The public setXXXX() and getXXXX() mthods are access points of the instance variables of the EncapTest class.
  Normally, these methods are referred to as getters and setters. Therefore, any class that wants to access the
  variables should access them through getters and setters.
  
                         public class RunCap{
                         public static void main(String args[]){
                         EncapTest encap = new EncapTest();
                         encap.setName("James");
                         encap.setAge(20);
                         encap.setIdNum("12343ms");
                         System.out.println("Name:" + encap.getName() + "Age:" + encap.getAge());
                             }
                            }
                         
  <h2>Benefits of Encapsulation</h2>        
  - the field of a class can be read-only or write-only
  - a class can have total control over what is stored in its fields
  - the users of a class do not know how the class stores its data. A class can change the data type of a field
    and users of the class do not need to change any of their code
    
