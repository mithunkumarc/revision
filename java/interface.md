An interface is an abstract data type that defines a list of abstract
public methods that any class implementing the interface must provide.  

Interfaces cannot be instantiated—they can only be implemented by classes or extended by other interfaces.  

An interface can also include a list of 
  
      constant variables and 
      default methods
      private methods
      static methods
      nested interfaces
    
1. class implements interface, Interface extends interface.
2. contract between interface and implementing class, class must provide implementation for abstract mehods.
3. class can either implement abstract method or keep them abstract and declare itself as abstract class.

#### purpose of interface 

      In Real world, many object share similar behaviour belong to different classes.
      Interface can share methods to different classes as methods are empty, will not create any conflict.

#### why default methods

      if a new abstract method is added to interface, all the classes which implemented this interface
      has to provide implementation even though they don't need it. if Default method is added to interface
      now class has option if they want to provide/override implementation.

#### If a class inherits same default method from two different interfaces
  

      interface First {
        default void method() {
          System.out.println("first");
        }
      }
      
      interface Second {
        default void method() {
          System.out.println("second");
        }
      }

      // this class has to override and declare it as public
      public class TestDefaultClass implements First, Second {
          // override method() here and mark it public
      }


#### why private methods

      some helper methods used by interface internally
  
#### why static methods

      As interface is not intended to create object, so it supports static methods
      Access static methods using Interface name
