#### final class : stops inheritance
    
            if a class dont want any other class to extend it.
            example : immutable class String.
            if string class is not final, people can change the way string works in subclass.

#### final local variable
          
            local variable must be initialized
            local final variable cannot be reinitialized
  
#### final instance variable 

            class Vehicle {
              final String companyName = "SomeCompany";// cant be changed
            }

#### final reference variable

            final Person p = new Person();
            // p cannot be reinitilized, means it cannot point to another person object

#### final method : stops polymorphism

            connot be overrided by can be inherited to child class( access modifier rules apply)
            

#### final static method
    
            static methods can be final
            static method inheritance :
            if static method is final in parent class, child class cannot replace it.
            
            class Animal {
                    public static final void somemethod() {

                    }
                }

            class Dog extends Animal {
                // error
                public static final void somemethod() {

                }
            }

#### blank final variable

            instance variable can final.
            if each object need a different final value the initialize in constructor.
            eg : vehicle reg number
            
            class Vehicle {
                final String regNum; // blank final var, initialized when object is created
                public Vehicle(String regNum) {
                    this.regNum = regNum;
                }
            }


#### final abstract class : abstract class cannot be final

            invalid identifier

#### final interface : interface cannot be final


            invalid identifier
