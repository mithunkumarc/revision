#### why oops

      to solve read world problems
      simulating real world problems to software solved by oops concepts.
      
      inheritance : reuse, scalable, modular
      encapsulation : data safety
      polymorphism : behaving different at differenct situations
      abstraction : igonoring unnecessary details, focusing on what is required

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
#### static polymorphism : overloading methods
#### dynamic polymorphism : overrding methods
#### impact of throws exception declaration on methods
