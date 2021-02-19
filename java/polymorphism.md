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
      
      rules
      
      


parent p = new Child();
p.name //parent name
p.callMethod(); // child overridden method if available else inherited


#### parent class ref var pointing to subclass object  (stuck to same hierarcy)

#### interface ref var pointing to implemented class object  (can be implemented on any hierarcy which supports behaviour)

staic poly morphism , dynamic  

static biding  
