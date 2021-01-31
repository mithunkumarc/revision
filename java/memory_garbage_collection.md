HEAP : 

        Java Heap space is used by java runtime to allocate memory to Objects and JRE classes. 
        Whenever we create an object, it’s always created in the Heap space.
        Garbage Collection runs on the heap memory to free the memory used by objects that don’t have any reference. 
        Any object created in the heap space has global access and can be referenced from anywhere of the application.
        note : java latest version how GC works and is finalize() deprecated?
        
        
Stack : 

      Stack memory is always referenced in LIFO (Last-In-First-Out) order. Whenever a method is invoked, 
      a new block is created in the stack memory for the method to hold local primitive values and reference to other objects in the method.

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
      
#### finalize
