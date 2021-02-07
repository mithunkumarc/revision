An interface is an abstract data type that defines a list of abstract
public methods that any class implementing the interface must provide.  

      // abstract keyword is optional here
      // interfaces are by default abstract
      abstract interface First {

      }

Interfaces cannot be instantiated—they can only be implemented by classes or extended by other interfaces.    
In abstract method, abstract keyword is optional.  

Interfaces used to achieve abstraction. Behaviour without implementation.  

Achieve multiple inheritance , one interface extends multiple interfaces.  

An interface can also include a list of  
  
      constant variables and
      abstract method : abstract keyword is optional
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



#### why private methods

      some helper methods used by interface internally
  
#### why static methods

      As interface is not intended to create object, so it supports static methods
      Access static methods using Interface name


#### polymorphism


			interface Flyable {
				public void fly();
			}

			// hierarchy flying vehicles
			class Helicoptor implements Flyable {
				@Override
				public void fly() {
					System.out.println("helicoptor fly");
				}
			}

			// bird hierarchy
			class Parrot implements Flyable {
				@Override
				public void fly() {
					System.out.println("parrot fly");
				}
			}

			public class TestFlyable {
				// polymorphic
				public void testFly(Flyable f) {
					f.fly();// if f is bird calls bird's fly method...likewise
				}
				public static void main(String[] args) {
					Flyable f1 = new Helicoptor();
					Flyable f2 = new Parrot();
					TestFlyable t = new TestFlyable();
					t.testFly(f1);
					t.testFly(f2);
				}
			}


#### single abstract method interface or Funtional interfaces

      Interface with single abstract method also called Functional interfaces.
      Single abstract method interfaces can be used to create lambdas
      
      abstract interface Squarable {
            public int square(int n);
      }
      
      Squarable s = new Squarable() {			
			@Override
			public int square(int n) {
				return n * n;
			}
		};
	System.out.println(s.square(5));

      //above code can be rewirtten as 
      Squarable s = (int n) -> n * n;
	System.out.println(s.square(5));

      //or, datatype int is optional
      Squarable s = n -> n * n;
      System.out.println(s.square(5));
      
      
#### If a interface inherits two or more methods which have same method name.

        a. abtract method

        interface First {
          abstract void method();
        }
        interface Second {
          abstract void method();
        }

        interface Third extends First, Second {
          // it doesn't matter which abstract method() it inherits both are empty
        }


        b. default method
        
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

        interface Third extends First, Second {
          // this method() has to override here, else error thrown
          default void method() {
            System.out.println("third");
          }
        }

        c. static method
        
        interface First {
          public static void method() {
            System.out.println("first");
          }
        }
        interface Second {
          public static void method() {
            System.out.println("second");
          }
        }

        interface Third extends First, Second {
            // neither from First or Second static method() not inherited here
        }
        
        // in main method, Third.method(); throws error

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
      
#### IF a class implements two interfaces, which have static method with same name      

      interface First {
        public static void method() {
          System.out.println("first");
        }
      }
      interface Second {
        public static void method() {
          System.out.println("second");
        }
      }
      
      // class need not to worry as static methods are called using respective interface name
      public class TestStatic implements First, Second {}

