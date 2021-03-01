1. Deadlock describes a situation where two or more threads are blocked forever, waiting for each other. 
2. Deadlock occurs when multiple threads need the same locks but obtain them in different order. 
3. A Java multithreaded program may suffer from the deadlock condition because the synchronized keyword 
causes the executing thread to block while waiting for the lock, or monitor, associated with the specified object. 



#### deadlock thread example

t1 has key1 and waiting for key2  
t2 has key2 and waiting for key1  
t1 and t2 will wait forever : deadlock  


        public class HelloWorld {
          private static String key1 = "First";
          private static String key2 = "Second";

          public static void main(String[] args) throws InterruptedException  {
            Thread t1 = new Thread(() -> {
              System.out.println("t1 waiting for key1 ");
              synchronized (key1) {
                // inject delay here to let another thread to get key2
                try{
                  Thread.sleep(2000);
                }catch(InterruptedException e) {}
                //
                System.out.println("t1 got key1");
                System.out.println("t1 waiting for key2");
                synchronized (key2) {
                  System.out.println("t1 got key2");
                }
              }
            });

            Thread t2 = new Thread(() -> {
              System.out.println("t2 waiting for key2");
              synchronized (key2) {
                // inject delay here to let another thread to get key1
                try{
                  Thread.sleep(2000);
                }catch(InterruptedException e) {}
                //
                System.out.println("t2 got key2");
                System.out.println("t2 waiting for key1");
                synchronized (key1) {
                  System.out.println("t2 got key1");
                }				
              }
            });


            t1.start();
            t2.start();
          }
        }

        /*
         *  t1 waiting for key1 
          t2 waiting for key2
          t1 got key1
          t1 waiting for key2
          t2 got key2
          t2 waiting for key1
         */

