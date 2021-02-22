
There are many immutable classes like 
        
        String, Boolean, Byte, Short, Integer, Long, Float, Double etc. 

In short, all the wrapper classes and String class is immutable.  
We can also create immutable class by creating final class that have final data members as the example given below:

#### Example to create Immutable class

In this example, we have created a final class named Employee. It have one final datamember, a parameterized constructor and getter method.

        // no subclass, because subclass can have access to parent members
        public final class Employee {
                // one time initialization through constructor
                final String pancardNumber;
                
                public Employee(String pancardNumber){  
                    this.pancardNumber = pancardNumber;  
                }  

                // read only : getter method
                public String getPancardNumber(){  
                  return pancardNumber;  
                }  
        }
        
The above class is immutable because:

1. The instance variable of the class is final i.e. we cannot change the value of it after creating an object.
2. The class is final so we cannot create the subclass.
3. There is no setter methods i.e. we have no option to change the value of the instance variable.
