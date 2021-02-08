#### why oops

      to solve read world problems
      simulating real world problems to software solved by oops concepts.
      
      inheritance : reuse, scalable, modular
      encapsulation : data safety
      polymorphism : behaving different at differenct situations
      abstraction : igonoring unnecessary details, focusing on what is required
      
#### example

      // assume both cass in same package
      class Animal {
            public String name;
            public void eat(){
                  //animal eat
            }
      }
      class Dog extends Animal {
            // Dog inherits name, eat
      }

#### how to achieve in java

      using extends keyword 

#### Object class : default superclass

      By default in java every class is a subclass of Object directly or indirectly.
      so Top most class in java is Object class.

#### inheritance : IS A relationship

      Class inherits properties from another classs
      Classes doesn't supprt multiple inheritance.
      Inheritance support multiple inheritance.
      child class can have other property along with inherited properties. 
      
#### why inheritance : 

      reuse code


#### super/base/parent class, child/subclass 

      parent class : top class is call parent class
      subclass : class which inherits properties from other class is called subclass
      
#### situation : parent and child class in same package
      
      By default all public, protected and default methods will be inherited to subclass
      Child class can hide(give new value other than parent) instance field or 
      override(change implemenatation) inheriting method.

#### situation : parent and child class in different package

      // package MainBranch
      package mainbranch;
      public class Manager {
            public String file1;
            protected String file2;
            String file3;
            private String file4;
      }

      // package SubBrach
      package subbranch;
      import mainbranch.Manager;
      public class BranchManager extends Manager {
            public void readFiles(Manager m) {
                  System.out.println(m.file1); // can read parent public copy
                  // cannot read protected, default and private property
                  System.out.println(this.file1); // public property inherited 
                  System.out.println(this.file2); // protected property inherited
                  //file3(default) and anyway file4 is private and is not inherited
            }
      }

      

#### impact of access modifiers while inheriting 
      
            public properties will be inherited to child class irrespective of packages
            protected properties will be inherited to child class within package and outside package.
            default properties will be inherited to child class within package.
            private properties never gets inherited.
            
            * child class can access only parent public property.
              protected, default and private(obivious) will not be accessed. 


#### constructors with inheritance

            not inherited as each class have their own constructors
            
#### child class constructors calls parent class constructors

                  class Animal {
                        public Animal() {
                              System.out.println("animal constructor");
                        }
                  }
                  class Dog extends Animal {
                        public Dog() {
                              System.out.println("dog constructor");
                        }
                  }

                  public class HelloWorld {

                        public static void main(String[] args) {
                              Dog d = new Dog();
                        }
                  }

                  /*
                   * output : 
                        animal constructor
                        dog constructor
                   * */

#### How child class constructor calls parent class constructors? using super keyword.
      
      by default super keyword will be added at the first line of child class constructor
      //super();
                 
                  class Animal {
                        public Animal() {
                              System.out.println("animal constructor");
                        }
                  }
                  class Dog extends Animal {
                        public Dog() {
                              super();//by default super keyword will be added here
                              System.out.println("dog constructor");
                        }
                  }
                  
#### why in java inheritance child class constructor calls parent class constructor.                 

      Constructors always initialize values to instances
      so inheriting values also need values which they belong to parent class.
      so Child class constructors calls parent class constructors to let initialize parent class properties first.
      
