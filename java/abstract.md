#### Abstract class : 
    
      can have instance variables
      constructors (even though cannot be instantiated: child class constructor call this)
      

some rules 

1. Abstract classes cannot be instantiated directly.

2. Abstract classes may be defined with any number, including zero, of abstract and nonabstract methods.

3. Abstract classes may not be marked as private or final.

4. An abstract class that extends another abstract class inherits all of its abstract methods
as its own abstract methods.

5. The first concrete class that extends an abstract class must provide an implementation
for all of the inherited abstract methods.


#### abstract method : 

1. Abstract methods may only be defined in abstract classes.

2. Abstract methods may not be declared private or final.

3. Abstract methods must not provide a method body/implementation in the abstract
class for which is it declared.

4. Implementing an abstract method in a subclass follows the same rules for overriding a
method. For example, the name and signature must be the same, and the visibility of
the method in the subclass must be at least as accessible as the method in the parent
class.

#### interfaces can have abstract methods, default methods, static methods and private methods



#### Abstract class vs Interface

    Abstract class : if we need instance with both state and behaviour
    Interface : if we need only behaviour but no state (only feature to be added)
    
 | Abstact classes     | Interfaces        |
 |:-------------------:| -----------------:|
 | instance variables/state | no instance variables, only constants |
 | abstract methods, implemented methods | abstract methods, default methods   |
 | multiple inheritance not allowed      | supports multiple inheritance    |
 | class extends abstract classes      | class implements inheritance    |


* Interface is also type, so its reference var can point to instance of implementing class

#### interface bring unrelated classes together


            Interface Flyable {
              fly();
            }

            
            class Helicopter implements Flyable
            class bird implements Flyable
            class Insect implements Flyable
            
            Flyable f1 = new Helicopter();
            Flyable f2 = new Bird();
            Flyable f3 = new Insect();
            
            // inside someclass
                public void makeFly(Flyable f){
                    // f can be Helicoptor or bird or Insect
                    f.fly();
                }
