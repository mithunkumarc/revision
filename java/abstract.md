#### Abstract class : class with abtract method.
    
      can have instance variables
      constructors (even though cannot be instantiated: child class constructor call this)
      public/default access modifiers allowed        
      can have static method
      
#### Why abstract class

        If we don’t know the behaviour of some action we can declare abstract method.
        Abstract helps to concentrate on designing projects
        Abstract methods force subclass to implement methods
        Its sole purpose, mission in life, is to be extended (subclassed).       

#### some rules 

1. Abstract classes cannot be instantiated directly. 
    Doesnt makes sense to create instance with out implementation.(object don't know how to behave)

2. Abstract classes may be defined with any number, including zero, of abstract and nonabstract methods.

3. Abstract classes may not be marked as private or final.

4. An abstract class that extends another abstract class inherits all of its abstract methods
as its own abstract methods.

5. The first concrete class that extends an abstract class must provide an implementation
for all of the inherited abstract methods.


#### Empty abstract class is allowed

        abstract class Car {

        }

#### Declaring abstract method

        // ends with semicolon without body
        // cannot be declared as final
        // It must be implemented in child class or concrete child class.
        // Abstract method must be inside a abstract class.
        public abstract void method();
        
#### Abstract class force subclass to implement

        abstract class GeometricShape {
            public abstract void draw();
        }

        class Circle extends GeometricShape {
            // circle has to give draw implementation
            public void draw() {
                // draw circle
            }
        }

#### If a class inherits abstract method, it has option to give implementation or maitain abstract

            abstract class GeometricShape {
                public abstract void draw();
            }

            abstract class Circle extends GeometricShape {
                // maintain draw method as abstract here
            }

#### what is concreate class

            last class in inheritance class hierarchy

#### Contrete class has to give implemention in abstract classes hierarchy 
    
        // if contrete class aslo abtract then we cannot create instance, no use of creating class hierarchy
        
        abstract class GeometricShape {
            public abstract void draw();
        }

        abstract class Circle extends GeometricShape {
            // maintain draw method as abstract here
        }

        // concrete class giving implementation
        // you can mark this class abstract too
        // if you cant create any instance from hierarchy of classes then no point of being created
        class BigCircle extends Circle {
            public void draw() {
                System.out.println("draw big circle");
            }
        }


#### Abstract class cannot be final

        abstract final class Car {} // class can be either abstract or final not both
        // the purpose of abstract class is to force subclass to give implementation
        // final will stop inheritance

#### Abstract class can have implemented methods

        abstract class Car {
            public void start(int n) {
                System.out.println("start");
            }
        }


#### Abstract class reference variable can point to its child class Instance

        abstract class Car {
            // some abstract methods
        }
        class MiniCar extends Car {
            // override abstract methods
        }
        
        // in main method
        Car c = new MiniCar();

#### abstract method : 

1. Abstract methods may only be defined in abstract classes.

2. Abstract methods may not be declared private or final.

3. Abstract methods must not provide a method body/implementation in the abstract
class for which is it declared.

4. Implementing an abstract method in a subclass follows the same rules for overriding a
method. For example, the name and signature must be the same, and the visibility of
the method in the subclass must be at least as accessible as the method in the parent
class.

#### interfaces can have 

    constants
    abstract methods, 
    default methods, 
    static methods and 
    private methods
    nested interface



#### Anonymous class : creating direct object instead of creating subclass

     Anonymous class : when to use : like use and throw situation, one instance
     class : when to use : situation where we have to create many objects 
     
#### Lambdas cannot be created from Anonymous class created from Abstract class.
    
    abstract class Car {
        public abstract int square(int n);
    }
    
    Car c = n -> n * n; // error  : must be functional interface
    
    * Lambdas can be created from functional interface only


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
