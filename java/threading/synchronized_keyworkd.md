#### RaceCondition : 

      Without synchronized keyword program may run into racecondition in multithreaded environment.

      Race condition in Java is a type of concurrency bug or issue which is introduced in your program 
      because parallel execution of your program by multiple threads at the same time.
      (end result may not be same as expected)



      /*
       * Account Instance has Withdraw method
       * Initial balance is 30
       * three threads created each thread calls withdraw method of same instance ten times
       * so final balance should be 0
       * but because all three threads access withdraw method at the same time race condition occurs
       * Thread sleep used only because to see race condition as threads are very quick(for concept).
       * */


        class Account implements Runnable {
          private int balance  = 30;
          @Override
          public void run() {
            for(int i = 1;i <= 10; i++) {
              try{Thread.sleep(100);}catch(InterruptedException e) {
                System.out.println("interrupted exception "+ e.getMessage());
              }
              this.withdraw(); // calling with draw method
              System.out.println("Bank Transaction : "+Thread.currentThread().getName() + " : balance "+ this.balance);
            }
          }	
          // no synchronized keyword is used here
          public void withdraw() {
            this.balance = this.balance - 1; // each thread deduct 1 at a time
          }

          public int getBalance() {
            return this.balance;
          }
        }

        public class HelloWorld {
          public static void main(String[] args) throws InterruptedException  {
            // target instance
            Account account1 = new Account();
            // three threads
            Thread t1 = new Thread(account1);
            Thread t2 = new Thread(account1);
            Thread t3 = new Thread(account1);
            t1.start();
            // purposefully delaying to see race condition
            try{Thread.sleep(100);}catch(InterruptedException e) {
              System.out.println("interrupted exception "+ e.getMessage());
            }
            t2.start();
            // purposefully delaying to see race condition
            try{Thread.sleep(100);}catch(InterruptedException e) {
              System.out.println("interrupted exception "+ e.getMessage());
            }
            t3.start();
          }
        }


#### Synchronized keyword

        It allows to execute method/block one at a time.
        First threach which access block/method will get lock.
        in case of method, instance of the method which is being acted on is a lock.
        we can use other object as lock also.



#### to fix racecondition, synchronized keyword is used: 

              
      class Account implements Runnable {
        private int balance  = 30;
        @Override
        public void run() {
          for(int i = 1;i <= 10; i++) {
            try{Thread.sleep(100);}catch(InterruptedException e) {
              System.out.println("interrupted exception "+ e.getMessage());
            }
            this.withdraw(); // calling with draw method
            System.out.println("Bank Transaction : "+Thread.currentThread().getName() + " : balance "+ this.balance);
          }
        }	
        // synchronized keyword is used here
        public synchronized void withdraw() {
          this.balance = this.balance - 1; // each thread deduct 1 at a time
        }

        public int getBalance() {
          return this.balance;
        }
      }

      public class HelloWorld {
        public static void main(String[] args) throws InterruptedException  {
          // target instance
          Account account1 = new Account();
          // three threads
          Thread t1 = new Thread(account1);
          Thread t2 = new Thread(account1);
          Thread t3 = new Thread(account1);
          t1.start();
          // purposefully delaying to see race condition
          try{Thread.sleep(100);}catch(InterruptedException e) {
            System.out.println("interrupted exception "+ e.getMessage());
          }
          t2.start();
          // purposefully delaying to see race condition
          try{Thread.sleep(100);}catch(InterruptedException e) {
            System.out.println("interrupted exception "+ e.getMessage());
          }
          t3.start();
        }
      }

#### Mutex : 

      A mutual exclusion (“Mutex”) is a mechanism that acts as a flag/lock to 
      prevent two threads from performing one or more actions simultaneously.


#### synchronized block. 
#### below example uses this(current object as lock). lock depends on logic.
#### lock is also called mutex.
#### mutex is chosen as whose state must be protected from multithreads(thread safe)


        class Account implements Runnable {
          private int balance  = 30;
          @Override
          public void run() {
            for(int i = 1;i <= 10; i++) {
              try{Thread.sleep(100);}catch(InterruptedException e) {
                System.out.println("interrupted exception "+ e.getMessage());
              }
              // synchronized block used here
              synchronized (this) {
                this.withdraw();
              }
              System.out.println("Bank Transaction : "+Thread.currentThread().getName() + " : balance "+ this.balance);
            }
          }	

          public synchronized void withdraw() {
            this.balance = this.balance - 1; // each thread deduct 1 at a time
          }

          public int getBalance() {
            return this.balance;
          }
        }

        public class HelloWorld {
          public static void main(String[] args) throws InterruptedException  {
            // target instance
            Account account1 = new Account();
            // three threads
            Thread t1 = new Thread(account1);
            Thread t2 = new Thread(account1);
            Thread t3 = new Thread(account1);
            t1.start();
            // purposefully delaying to see race condition
            try{Thread.sleep(100);}catch(InterruptedException e) {
              System.out.println("interrupted exception "+ e.getMessage());
            }
            t2.start();
            // purposefully delaying to see race condition
            try{Thread.sleep(100);}catch(InterruptedException e) {
              System.out.println("interrupted exception "+ e.getMessage());
            }
            t3.start();
          }
        }







