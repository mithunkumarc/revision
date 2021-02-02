

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
        
