#### polymorphism : one object taking many forms(behaviour)

Polymorphism is the capability of a method to do different things based on the object that it is acting upon. 
In other words, polymorphism allows you to define one interface(methods) and have multiple implementations.

The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object.  
  
    Parent p = new Child();

Inheritance and polymorphism will go hand in hand. Without inheritance there is no polymorphism.


1. overloading methods

2. overriding methods

parent p = new Child();
p.name //parent name
p.callMethod(); // child overridden method if available else inherited

parern class ref var pointing to subclass object  
interface ref var pointing to implemented class object  

staic poly morphism , dynamic  

static biding  
