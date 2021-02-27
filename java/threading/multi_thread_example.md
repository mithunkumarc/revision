
#### multi thread example, setName used to provide custom name for thread

        class BankTransaction implements Runnable {
          @Override
          public void run() {
            for(int i = 1;i < 10; i++) {
              System.out.println("Bank Transaction : "+Thread.currentThread().getName());
            }
          }
        }

        public class HelloWorld {
          public static void main(String[] args) {
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
            t2.start();
            t3.start();
          }
        }


#### inject delay in multithreading using Thread.sleep(milliseconds)

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
          public static void main(String[] args) {
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
            t2.start();
            t3.start();
          }
        }
