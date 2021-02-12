
#### object class : 

        Class Object is the root of the class hierarchy. 
        Every class has Object as a superclass. 
        All objects, including arrays, implement the methods of this class.

#### methods

##### clone : 

        protected Object	clone()	
        Creates and returns a copy of this object.

#### equals

        boolean	equals​(Object obj)	
        Indicates whether some other object is "equal to" this one.

         * know the difference == and .equals()
         == operator, .equals method
         == used between variables/reference variables pointing to same object or not
         equals checks content

#### finalize() : deprecated in java 11

        protected void	finalize()	
        Deprecated.
        perform cleanup actions before the object is irrevocably discarded. 
        jvm decides when to run, called only once. (not guarantee that it will run)
        The finalization mechanism is inherently problematic.
        * The Cleaner and PhantomReference provide more flexible and efficient ways to release resources when an 
        object becomes unreachable.
        
        Finalization can lead to performance issues, deadlocks, and hangs. 
        Errors in finalizers can lead to resource leaks; 
        there is no way to cancel finalization if it is no longer necessary; 
        and no ordering is specified among calls to finalize methods of different objects. Furthermore, 
        there are no guarantees regarding the timing of finalization. 
        The finalize method might be called on a finalizable object only after an indefinite delay, if at all. 
        Classes whose instances hold non-heap resources should provide a method to enable explicit release of those resources, 
        and they should also implement AutoCloseable if appropriate

##### getClass() : class name

        Class<?>	getClass()	
        Returns the runtime class of this Object.

###### hashCode() : 

        int	hashCode()	
        Returns a hash code value for the object.

##### notify() : notifyAll()

        void	notify()	
        Wakes up a single thread that is waiting on this object's monitor.

        void	notifyAll()	
        Wakes up all threads that are waiting on this object's monitor.

##### toString() 

        String	toString()	
        Returns a string representation of the object.

##### wait() :

        //overloaded with time millisenconds
        void	wait()	
        Causes the current thread to wait until it is awakened, typically by being notified or interrupted.
