#### Exception

An exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions.
The Java programming language uses exceptions to handle errors and other exceptional events.

#### purpose

        program fails for many reasons, 
        some of them are coding problems (Nullpointer/ArrayIndexOutofBound) and some of them are not.(Internet down-rest api)
        Exceptions can help program to recover from this situation with proper message to user.
        Either API author/designer can handle exception or he/she can make user/api-caller to handle it.

#### hierarchy

        + java.lang.Object
        + ------- java.lang.throwable
                  +-------------------- Errors
                  +-------------------- Exceptions
                                        + ---------- Other compile time exceptions
                                        + ---------- run time excetptions


#### Errors

      subclass of throwable
      indicates serious problems that a reasonable application should not try to catch. 
      errors are abnormal conditions that should never occur.
      
      eg : 
      IOError
      VirtualMachineError :  JVM is broken or has run out of resources necessary for it to continue operating.
            OutOfMemoryError, 
            StackOverflowError


#### StackOverFlowError :

        Thrown when a stack overflow occurs because an application recurses too deeply.
        Stack is used for execution of methods. 
        For every method call, one frame or block is created in the stack memory. 
        The data related to method like parameters, local variables or references to objects are stored in this block. 
        When the method finishes its execution, this block is removed from the stack along with data stored in it.
        Whenever you call a method, it must finish its execution and leave the stack memory. 
        If your methods are staying in the stack then stack will be full and JVM will throw java.lang.StackOverflowError.

#### OutOFMemoryError : 

        java.lang.OutOfMemoryError is thrown when the heap is full and 
        JVM is unable to allocate the memory to new objects.

        The objects you create in java are stored in the heap memory. 
        When the objects are no more required, they must be removed from the memory. 
        Garbage collector removes the unwanted objects from the heap memory. 
        If your objects have live references, garbage collector doesn’t remove them. 
        It removes only those objects which don’t have live references.
        If there is no space left for new objects in the heap memory then JVM will throw java.lang.OutOfMemoryError.


#### compile time exception examples

        IOException
            FileNotFoundException : handle at compile time if file not exists
        SQLException : driver/credentials/port/query
        

#### runtime exception examples

        ClassCastexception
        ArithmeticException  : divided by zero
        ArrayIndexOutOfBound
        NullPointer

#### checked/compiletime/caught exception vs unchecked/runtime/uncaught exception

        compile time : 
        occurs at compile time.
        should be handle at compile time else compiler throws error.
        
        
        Run time : occurs at runtime. should not be handled, instead fix it.
        
          if(arraysize > arraylength) {
              //
          }
          if(myObject != null) {
            //
          }


#### userDefinedException

#### impact of method throws exception with overriding

#### return inside try catch finally
