#### Thread : 

  it is a class in java.
  means separte path of execution.
  Java Thread is a lightweight process that executes some task.
  each thread has its own call stack. [call stack : who called who: stacktrace]
   
#### why thread is lightweigh process : 

    Threads are sometimes called lightweight processes because they have their own stack but can access shared data. 
    Because threads share the same address space as the process and other threads within the process, 
    the operational cost of communication between the threads is low. 

#### user thread : 

          Non JVM thread, thread created by user(programmer).
          JVM will not exit until all user threads complete their execution

#### daemon thread

          JVM thread. 
          background supporting tasks which helps user thread to run.
          example ; Garbage collector
          JVM will exit when all user threads completes but still daemon threads are running.
           
           
