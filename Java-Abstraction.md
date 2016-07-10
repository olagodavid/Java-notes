# Java - Abstraction

What is Abstraction?
Abstraction is process of hiding the implementation details and showing only the functionality.

Abstraction in java is achieved by using interface and abstract class. Interface give 100% abstraction and abstract class give 0-100% abstraction.

What is Abstract class in Java?
 A class that is declared as abstract is known as abstract class.

###Syntax:
abstract class <class-name>{}

An abstract class is something which is incomplete and you cannot create instance of abstract class.
If you want to use it you need to make it complete or concrete by extending it.
A class is called concrete if it does not contain any abstract method and implements all abstract method inherited from abstract class or interface it has implemented or extended.

What is Abstract method in Java?

A method that is declare as abstract and does not have implementation is known as abstract method.
If you define abstract method than class must be abstract.

###Syntax:

abstract return_type method_name ();

An abstract method in Java doesn't have body, it’s just a declaration. In order to use abstract method you need to override that method in Subclass.

Example 1 :( Without abstract method)

```java

class Employee extends Person {
    
    private String empCode;

    public String getEmpCode() {
        return empCode;
    }

    public void setEmpCode(String empCode) {
        this.empCode = empCode;
    }
    
    
}

abstract  class Person {
    
    private String name;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
    
    

}

public class Main{
	public static void main(String args[]){
        //INSTIATING AN ABSTRACT CLASS GIVES COMPILE TIME ERROR
        //Person p =  new Person() ;
        
        
        //THIS REFERENCE VARIABLE CAN ACESS ONLY THOSE METHOD WHICH ARE OVERRIDDEN
        Person person = new Employee();
        person.setName("Jatin Kansagara");        
        System.out.println(person.getName());
    }
}
```

Example 2: (with abstract method)

```java

public class Main{
	public static void main(String args[]){
        TwoWheeler test = new Honda();
        test.run();
    }
}
abstract  class TwoWheeler {
    public abstract void run();
}
class Honda extends TwoWheeler{
	public void run(){
		System.out.println("Running..");
	}
}
```
When do you use abstraction?
When you know something needs to be there but not sure how exactly it should look like.

Advantages of Abstraction
By using abstraction, we can separate the things that can be grouped to another type.

Frequently changing properties and methods can be grouped to a separate type so that the main type need not undergo changes. This adds strength to the OOAD principle -"Code should be open for Extension but closed for Modification".

Simplifies the representation of the domain models.


Summary:
-    Use abstraction if you know something needs to be in class but implementation of that varies.
-     In Java you cannot create instance of abstract class , its compiler error.
-    abstract is a keyword in java.
-    A class automatically becomes abstract class when any of its method declared as abstract.
-     abstract method doesn't have method body.
-    Variable cannot be made abstract, its only behavior or methods which would be abstract.
-    If a class extends an abstract class or interface it has to provide implementation to all its abstract method to be a concrete class. Alternatively this class can also be abstract.



