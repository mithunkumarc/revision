#### Thread : 

  it is a class in java.
  means separte path of execution.
  Java Thread is a lightweight process that executes some task.
  each thread has its own call stack. [call stack : who called who: stacktrace]
   
#### why thread is lightweight process : 

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
          
          the JVM exits an application only when all user threads are complete—the JVM doesn’t
          care about letting daemon threads complete, so once all user threads are
          complete, the JVM will shut down, regardless of the state of any daemon
          threads.

#### Main Thread : 

          The Main thread in Java is the one that begins executing when the program starts. 
          All the child threads are spawned from the Main thread. 
          Also, it is the last thread to finish execution as various shut-down actions are performed by it.

#### Thread Scheduler

        Thread scheduler is the part of Operating System implementation and when a Thread is started, 
        it’s execution is controlled by Thread Scheduler and JVM doesn’t have any control on it’s execution.

        eg : picking which thread to be executed

#### ways to create Thread in Java

        Extend the java.lang.Thread class.
        Implement the Runnable interface.


#### Extending thread class
        
1. when you want your class to behave like thread
2. not recommended
3. use start() to run your class as thread
4. if run() called directly, new thread will not be created, it runs in main thread.
5. Main thread will not stop when it creates new/child thread, it will go on with its task and complete.
6. child thread by default named from thread-0, thread-1...

        class MyThread extends Thread {
          @Override
          public void run() {           
            System.out.println("running in separate thread : "+ Thread.currentThread().getName());
          }
        }

        public class HelloWorld {
          public static void main(String[] args) {
            System.out.println("Before creating user thread, which thread is running? : "+ Thread.currentThread().getName());
            MyThread mt = new MyThread();
            mt.start();		
            System.out.println("End of Main thread"); // main thread will not stop till all new thread to complete
          }
        }

output : 

        Before creating user thread, which thread is running? : main
        End of Main thread
        running in separate thread : Thread-0


#### Implement the Runnable interface: recommended way of creating thread in Java


1. create a class which implements runnable
2. runnable interface has method call run, implement in your class
3. create instance of your class and pass it to thread instance
4. start the thread
5. recommended way to create thread, if you just want to create a separate path of execution.
6. by this way, you still have chance to extend on more class


        class MyRunnable implements Runnable {
          @Override
          public void run() {
            System.out.println("running in separate thread : "+ Thread.currentThread().getName());
          }
        }

        public class HelloWorld {
          public static void main(String[] args) {
            System.out.println("Before creating user thread, which thread is running? : "+ Thread.currentThread().getName());
            MyRunnable myRunnable = new MyRunnable();
            Thread t = new Thread(myRunnable);
            t.start();
            System.out.println("End of Main thread");
          }
        }


#### Running thread as Anonymous class

        public class HelloWorld {
          public static void main(String[] args) {
            System.out.println("Before creating user thread, which thread is running? : "+ Thread.currentThread().getName());
            Thread t = new Thread(new Runnable() {			
              @Override
              public void run() {
                System.out.println("running in separate thread : "+ Thread.currentThread().getName());				
              }
            });
            t.start();
            System.out.println("End of main thread");
          }
        }


#### Running thread as lambda expression: replacing Anonymous class


        // Runnable as functional interface
        public class HelloWorld {
          public static void main(String[] args) {
            System.out.println("Before creating user thread, which thread is running? : "+ Thread.currentThread().getName());
            Thread t = new Thread(() -> 
                System.out.println("running in separate thread : "+ Thread.currentThread().getName())					
            );
            t.start();
            System.out.println("End of main thread");
          }
        }

