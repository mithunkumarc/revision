Thread states


        New -> Runnable -> Running -> Dead
                                      Waiting -> Runnable
                                      

1. New : Thread instance has been created but not start() method is called
2. Runnable : when start() is called thread enter to Runnable, waiting for Thread schedular to pick.
3. Running : Thread schedular picks thread to execute
4. Waiting/Blocked/Sleeping : io operations or waiting for object lock or sleep() being called on thread
5. Dead : thread has completed run() method.

* after completing wait/sleep thread will not go back to running, it will goto runnable state.
* sleep is a static method: currently running thread goto sleep.


#### Thread priority :  

        priority will be 1 to 10.
        default priority for all the threads is 5.
        
        Don’t rely on thread priorities when designing your multithreaded application. 
        Because thread-scheduling priority behavior is not guaranteed,
        it’s better to avoid modifying thread priorities. Usually, default priority will
        be fine.

        syntax : 
        Thread t = new Thread(runnableObject);
        t.setPriority(8);
        t.start();
        
#### Thread yeild static method :

        yield() is supposed to do is make the currently running thread head back to runnable 
        to allow other threads of the same priority to get their turn. 
        
        A yield() won’t ever cause a thread to go to the waiting/sleeping/blocking state. 
        At most, a yield() will cause a thread to go from running to runnable, 
        but again, it might have no effect at all.
        
#### Thread join method : 
      
      One thread “join onto the end” of another thread
      Lets say there are two threads A and B.
      Thread B has to start as soon as Thread A completed.
      If Thread B has to joing Thread A. use join method on A.
        
      Thread t1 = new Thread(b1);
      Thread t2 = new Thread(b2);
      Thread t3 = new Thread(b3);
      t1.setName("savings");
      t2.setName("loan");
      t3.setName("insurance");
      t1.start();
      t1.join(); //t2 will be started only when t1 completes
      t2.start();
      t2.join(); //t3 will be started only when t2 completes
      t3.start();
      
      // full example
      class BankTransaction implements Runnable {
        @Override
        public void run() {
          for(int i = 1;i < 10; i++) {
            try{Thread.sleep(100);}catch(InterruptedException e) {
              System.out.println("interrupted exception "+ e.getMessage());
            }
            System.out.println("Bank Transaction : "+Thread.currentThread().getName());
          }
        }
      }

      public class HelloWorld {
        public static void main(String[] args) throws InterruptedException  {
          BankTransaction b1 = new BankTransaction();
          BankTransaction b2 = new BankTransaction();
          BankTransaction b3 = new BankTransaction();
          Thread t1 = new Thread(b1);
          Thread t2 = new Thread(b2);
          Thread t3 = new Thread(b3);
          t1.setName("savings");
          t2.setName("loan");
          t3.setName("insurance");
          t1.start();
          t1.join(); //t2 will be started only when t1 completes
          t2.start();
          t2.join(); //t3 will be started only when t2 completes
          t3.start();
        }
      }
