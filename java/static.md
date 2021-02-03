#### why static 

        The static keyword in java is used for memory management mainly.
        if all objects of same class need same(shared) info then we can use static field in class

        can be applied to : 

                variables, 
                methods, 
                blocks and 
                nested class

        outer class, interface cannot be static
        
        ●	They can only call other static methods.
        ●	They can only access static data.
        ●	They cannot refer to this or super in any way.


#### Access static member

        To access static member , no need to create object, we can access static member directly using className.
        Static members saved in class area along with class, so static methods cannot access instance variables.

#### static methods can be overloaded

#### are static methods overrided? no , they can be hidden

        A hidden method occurs when a child class defines a static method with the same name
        and signature as a static method defi ned in a parent class. Method hiding is similar but
        not exactly the same as method overriding. 

        1. The method in the child class must have the same signature as the method in the parent
        class.
        2. The method in the child class must be at least as accessible or more accessible than the
        method in the parent class.
        3. The method in the child class may not throw a checked exception that is new or
        broader than the class of any exception thrown in the parent class method.
        4. If the method returns a value, it must be the same or a subclass of the method in the
        parent class, known as covariant return types.
        5. The method defined in the child class must be marked as static if it is marked as
        static in the parent class (method hiding). Likewise, the method must not be marked
        as static in the child class if it is not marked as static in the parent class (method
        overriding).

        Note that the first four are the same as the rules for overriding a method.


          public class Bear {
             public static void eat() {
              System.out.println("Bear is eating");
             }
          }
          public class Panda extends Bear {
             public static void eat() {
              System.out.println("Panda bear is chewing");
             }

            public static void main(String[] args) {
               Panda.eat();
           }
           
#### static final mehtod
        
        tobe updated
        
#### static vs instance calls



| Type        | Calling           | Legal?  | How? |
| ------------- |:-------------:| -----:| :---:  |
| Static method      | Another static method or variable | Yes |  Using the classname  |
| Static method      |  An instance method or variable      |   No |  |
| Instance method | A static method or variable      |    Yes |  Using the classname or a reference variable |
| Instance method |  Another instance method or variable      |    Yes |  Using a reference variable |


#### static variables
        
        shared by all instances, accessed by reference var/classname
        example usage : counter
        using final keyword with static variable makes it constant. eg : pi = 3.14;
        can point to object(becomes Static object)
        

#### static methods

        access modifiers can be applied
        called using reference var/classname
        can access other static methods, cannot access instance variables, cannot call instance methods.
        static methods are inherited
        can static method be final? yes. In the child class this cannot be hidden.
        static methods can be private.
        static methods can be overloaded
        static methods are inherited
        static methods cannot be overriden but hidden. (code semantic same as overriding though)
        
        
#### static blocks

        static blocks used for initialization
        executed when class is loaded
        executed even before main method gets executed
        parent static blocks are executed first and child static blocks are executed(parent-child class)
        
        
        Static blocks are executed when class are loaded into memory.

        When subclass object is created, static block of parent class executed first because 
        parent class loaded first then subclass static block is executed when subclass is loaded into memory.

        
        
#### order of initialization

                package basics;
                class Animal{
                        static {
                                System.out.println("animal static block");
                        }
                }
                class Dog extends Animal{
                        static {
                                System.out.println("dog static block");
                        }
                }
                class LabradorDog extends Dog{
                        static {
                                // skipped, as LabradorDog not instantiated(or its child child class)
                                System.out.println("labrador static block");
                        }
                }
                public class HelloWorld {
                        static{
                                System.out.println("helloworld static block");
                        }	
                        public static void main(String[] args) {
                                LabradorDog.class.toString();
                                Dog l = new Dog();
                        }
                }

                /*
                 * output : 
                 * 	helloworld static block
                        animal static block
                        dog static block

                 * */

