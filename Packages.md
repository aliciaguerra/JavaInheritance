Packages are used in Java in order to prevent naming conflicts, to control access, to make searching/locating
and uses of classes, interfaces, enumerations, and annotations easier, etc.

A package can be defined as a group of related types (classes, interfaces, enumerations, and annotations) providing
access protection and name space management.

Some of the existing packages in Java are:
 - java.lang - bundles the fundamental classes
 - java.io - classes for input, output functions are bundled in this package
 
Programmers can define their own packages to bundle group of classes/interfaces, etc. It is a good practice to
group related classes implemented by you so that a programmer can easily determine that the classes, interfaces,
enumerations, annotations are related.

Since the package creates a new namespace there won't be any name conflicts with names in other packages. Using packages,
it is easier to provide access control and it is easier to locate their related classes.

<h2>Creating A Package</h2>
While creating a package, you should choose a name for the package and include a package statement along with 
that name at the top of every source file that contains the classes, interfaces, enumerations, and annotation types that
you want to return in the pckage.

The package statement should be the first line in the source line. There can be only one package statement in each
source file, and it applies to all types in the file.

If a package statement is not used, then the classes, interfaces, enumerations, and annotation types will be placed in the
in the current default package.

To compile the Java programs with package statements you have to use the -d option as shown below:

                                           javac -d Destination_folder file_name.java
                                           
Then a folder with the given package name is created in the specified destination, and the compiled class files
will be placed in the folder.

<h2>Example</h2>
Let us look at an example that creates a package called animals. It is a good practice to use names of packages
with lower case letters to avid any conflicts with the names of classes, interfaces.

                                 package animals;
                                 interface Animal {
                                 public void eat();
                                 public void travel();
                                 }
 
 Now, let us implement the above interface in the same package animals:
 
                                  package animals;
                                  public class MammalInt implements Animal {
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
                                    
 <h2>The import Keyword</h2>
 If a class wants to use another class in the same package, the package name does not need to get used. Classes
 in the same package find each other without any special syntax.
 
 <h2>Example</h2>
 Here, a class named Boss is added to the payroll package that already contains Employee. The boss can then refer
 to the Employee class without using the payroll prefix.
 
                                      package payroll;
                                      public class Boss{
                                      public void payEmployee(Employee e){
                                      e.mailCheck();
                                          }
                                      }
                                      
 What happens if the Employee class is not in the payroll package? The Boss class must then use one of the 
 following techniques for referring to a class in a different package. 
 
                                        payroll.Employee
                                        
 The package can be imported using the import keyword and the wild card(*)
 
                                        import payroll.*;
                                        
                                       
                                        import payroll.Employee;
 
 A class file can contain any number of import statements. The import statements must appear after the package statement 
 and before the import declaration.
 
 <h2>The Directory Structure of Packages</h2>
 Two major results occur when a class is placed in a package:
 - The name of the package becomes a part of the name of the class, as we just discussed in the previous section.
 - The name of the package must match the directory structure where the corresponding bytecode survives.
 
Put the source code for a class, interface, enumeration, or annotation type in a text file whose name is the simple
name of the type and the extension is .java.

                                         package vehicle;
                                         public class Car{
                                         //Class implementation
                                         }
