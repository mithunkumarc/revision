HEAP : 

        Java Heap space is used by java runtime to allocate memory to Objects and JRE classes. 
        Whenever we create an object, it’s always created in the Heap space.
        Garbage Collection runs on the heap memory to free the memory used by objects that don’t have any reference. 
        Any object created in the heap space has global access and can be referenced from anywhere of the application.
        note : java latest version how GC works and is finalize() deprecated?
        
        
Stack : 

      Stack memory is always referenced in LIFO (Last-In-First-Out) order. Whenever a method is invoked, 
      a new block is created in the stack memory for the method to hold local primitive values and reference to 
      other objects in the method.

      Java Stack memory is used for the execution of a thread. 

      They contain method-specific values(local var values) that are short-lived and references to other objects in the heap 
      that is getting referred from the method.

      As soon as the method ends, the block becomes unused and becomes available for the next method.
      Stack memory size is very less compared to Heap memory.
      
      method call (and its order) stored in stack
      
      Each thread in a Java application has its own stack. The stack is used to hold return addresses, function/method call arguments, 
      

#### set heap memory : 

    -Xms :  initial memory allocation pool for JVM.
    -Xmx :  maximum memory allocation pool for JVM.
    * java.lang.OutOfMemoryError
    
#### set stack memory

    -Xss :  to define the stack memory size. (set thread stack size)
    * StackOverflowError

     stack memory is very fast when compared to heap memory.

     Stack memory is short-lived whereas heap memory lives from the start till the end of application execution.


#### Young Generation/Old Generation??

#### Garbage collection

      unreferenced objects are garbage collected
      when garbage collector has to start, decided by JVM
      request to run garbage collection : System.gc(); // still decided by JVM
      
      tobe updated...
      https://data-flair.training/blogs/garbage-collection-in-java/
      
#### object finalize method

        finalize method runs before garbage collector is executed/runs.
        no guarantee that it runs. runs 0 or 1 time.

#### why avoid finalize()

        finalize() is only run when the object is eligible for garbage collection. 
        The problem here is that by the end of the method, the object is no longer eligible for garbage
        collection because a static variable is referring to it and static variables stay in scope until
        the program ends. Java is smart enough to realize this and aborts the attempt to throw out
        the object. Now suppose later in the program objects is set to null. Oh, good, we can
        finally remove the object from memory. Java remembers already running finalize() on
        this object and will not do so again. The lesson is that the finalize() call could run zero
        or one time. This is the exact same lesson as the simple example—that’s why it’s so easy to
        remember.
        
        other drawback of finalize
        
        in particular, they can be run unexpectedly when an object becomes unreachable unexpectedly (but correctly); 
        finalization can easily break subclass/superclass relationships
        there is no ordering among finalizers
        a given object's finalize method is invoked at most once by the JVM, even if that object is "resurrected"
        there are no guarantees about timeliness of finalization or even that it will run at all
        there is no explicit registration or deregistration mechanism
        
        

        finalize() methods do not work in chaining like constructors. 
        It means when you call a constructor then constructors of all superclasses will be invoked implicitly. 
        But, in case of finalize() methods, this is not followed. 
        Ideally, parent class’s finalize() should be called explicitly but it does not happen.
        Suppose, you created a class and wrote its finalize method with care. 
        Someone comes and extend your class and does not call super.finalize() in subclass’s finalize() block, 
        then super class’s finalize() will never be invoked anyhow.

        Any exception which is thrown by finalize method is ignored by GC thread and it will not be propagated further, 
        in fact it will not be logged in your log files. So bad, isn’t it?


