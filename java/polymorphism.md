#### polymorphism : one object taking many forms(behaviour)

It is the capability of a method to do different things based on the object that it is acting upon. 
In other words, polymorphism allows you to define one interface(methods) and have multiple implementations.

The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object.  
  
    Parent p = new Child();
    List mylist = new ArrayList(); // mylist can be ArrayList and also any other instance implemented List interface

Inheritance and polymorphism will go hand in hand.  
Without inheritance there is no polymorphism.


1. overloading methods : static polymorphism
    
      more then one method is created with same name but different returntype or different parameters(or order of parameters)
      name of the methods must be same.
      access modifiers can be same or different.
      static is also optional and static methods also can be overloaded
      parameters must be different or their order of appearance must be different
      return type is optional, can be different or same
      

          public void eat(int i, String name) {
          }
          protected static void eat(String name, int i) {
          }
          static int eat(int i, String name, boolean b) {
            return 0;
          }

2. overriding methods : dynamic polymorphism

          when subclass inherits the method from parent class.
          subclass has oppertunity to use inherited or change the implementation.
          when subclass change the implementation method becomes overridden.

#### overriding rules
        
1. method signature must be same
2. access modifiers must not be more restrictive than parent method

        class Animal {
          public void eat() {
            System.out.println("animal eat");
          }
        }
        class Dog extends Animal {
          // error, parent method is public, all rest are restrictive
          void eat() {
            System.out.println("dog eat");
          }
        }

      if parent method is protected, subclass method can be protected and public
      if parent method is default, subclass method can be protected, default and public

      private > default > protected > public

3. final methods cannot be overidden

          final method can be inherited but cannot be overridded
      
5. should be having same parameter/argument list   

        class Animal {
          public void eat(String name, int age) {
            System.out.println("animal");
          }
        }
        class Dog extends Animal {
          public void eat(String name, int age) {
            System.out.println("eat");
          }
        }

5. method must be having same return type or subtype(covariant)


            class Animal {
            }
            class Dog extends Animal {
            }

            class Zoo {
              public Animal getAnimal() {
                return new Animal();
              }
            }
            class MiniZoo {
              public Dog getAnimal() {
                return new Dog();
              }
            }



6. A static method in a subclass may hide another static one in a superclass, and that’s called hiding.

          class Animal {
            static void eat() {
              System.out.println("animal");
            }
          }
          class Dog extends Animal {
            // this is not overriding, this is hiding
            // replacing inherited with new one
            static void eat() {
              System.out.println("eat");
            }
          }

#### polymorphic

        parent p = new Child();
        p.name //parent name
        p.callMethod(); // child overridden method if available else inherited


#### parent class ref var pointing to subclass object  (stuck to same hierarcy)

#### interface ref var pointing to implemented class object  (can be implemented on any hierarcy which supports behaviour)

staic poly morphism , dynamic  

static biding  
