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


#### throws : warning to caller to handle exception

        used on method declaration
        mandatory for compile time exception, optional for runtime exception so is try catch in this case
        


#### throw

        creating instance of exception inside method


#### method which throw runtime exception may not need throws declaration(so no to need try catch)
         
                // runtime exception example
                class UserNotFoundException extends RuntimeException {
                        private String message;
                        public UserNotFoundException(String message) {
                                this.message = message;
                        }
                        @Override
                        public String getMessage() {
                                return this.message;
                        }
                }

                // inside some class which uses runtime exception
                public void checkUser() throws UserNotFoundException { //throws not at all required
                        //check for user
                        throw new UserNotFoundException("user not found");
                }

#### user defined runtime exception : no need throws keyword as it is runtime exception

                // do we need runtime exception?????
                class UserNotFoundException extends RuntimeException {
                        private String message;
                        public UserNotFoundException(String message) {
                                this.message = message;
                        }
                        @Override
                        public String getMessage() {
                                return this.message;
                        }
                }

                public class TestException {
                        public static void main(String[] args) {
                                TestException te = new TestException();
                                te.checkUser();
                        }
                        public void checkUser() {
                                //check for user
                                throw new UserNotFoundException("user not found");
                        }
                }



#### user defined compile time exception

                // extends Exception
                // getMessage()
                // designer makes throws declartion on method
                // throw exception if something goes wrong
                // user will hanlde using try and catch
                class UserNotFoundException extends Exception {
                        private String message;
                        public UserNotFoundException(String message) {
                                this.message = message;
                        }
                        @Override
                        public String getMessage() {
                                return this.message;
                        }
                }

                public class TestException {
                        public static void main(String[] args) {
                                TestException te = new TestException();
                                try{
                                        te.checkUser();
                                } catch(UserNotFoundException u) {
                                        System.out.println(u.getMessage());
                                }
                        }
                        public void checkUser() throws UserNotFoundException{
                                //check for user
                                throw new UserNotFoundException("user not found");
                        }
                }



#### impact of method throws exception with overriding

##### If the superclass method does not declare an exception

        subclass overridden method cannot declare the checked exception but 
        it can declare unchecked/runtime exception.
        

        class Animal {
                // no exception declared here
                public void eat() {

                }
        }

        class Dog extends Animal {
                // error : cannot declare checked/compile time exception, runtime excetion allowed
                public void eat() throws Exception {

                }
        }

        
##### If the superclass method declares an exception

        1. subclass overridden method can declare same exception or skip declaring it.
        2. sublcass overriden method can declare subclass exception or but cannot declare parent exception.

#### return inside try catch finally

        try, catch , finally and throw throws keywords are used to handle exception
        
        // always finally block wins, even after providing return statements in try and catch
        try {
                //return 1; // finally block wins
                throw new Exception(); // finally block wins
        }
        catch(Exception e) {
                return 2; // finally block wins
        }
        finally {
                return 3;
        }
        
        
#### order of exception

        best practice : specific functions must be handled first , at the end handle generic exception.
        Generic Exception must be handled at last.

#### try catch finally rules

        only one try block allowed at a time.
        nested try-catch-finally allowed inside try block.
        multiple catch block allowed after try block.
        try must be follwed by either catch or finally.
        you can skip catch block but it is not a best practice.
        always log message in catch block.
        only one finally block is allowed.
        try-catch-finally allowed in finally block.

#### java 7 syntax of handling multiple catch block

		boolean flag = true;
		try {
			if(flag) {
				throw new SQLException();
			} else {
				throw new IOException();
			}
		} catch(SQLException | IOException e) {
		    //logger.log(e);

		} catch(Exception e) {
		    //logger.severe(e);
		}	
