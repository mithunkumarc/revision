#### Example

    /*
    Customer class  
      WithDraw - thread1 try to withdraw, if amount insufficient it will wait till balance deposited.
      Deposit - thread2 add amount to customer account and notify customer.
      withDraw and deposit both methods are synchronized.
    */

        class Customer {
          private int balance;

          public Customer(int balance) {
            this.balance = balance;
          }

          public synchronized void withDraw(int amount) {
            if(amount > this.balance) {
              try {
                System.out.println(amount + ": rupees not sufficient, waiting for balance.");
                this.wait();
                this.balance = this.balance - amount;
                System.out.println("remaining balance : "+ this.balance);
              } catch(InterruptedException e) {

              }
            } else {
              this.balance = this.balance - amount;
              System.out.println("remaining balance : "+this.balance+ " rupees.");
            }
          }

          public synchronized void deposit(int amount) {
            this.balance = this.balance + amount;
            this.notify();
            System.out.println("amount "+amount+" rupees deposited.");
          }

        }

        public class HelloWorld {
          public static void main(String[] args) {
            Customer c = new Customer(500);
            Thread t1 = new Thread(new Runnable() {			
              @Override
              public void run() {				
                c.withDraw(1000);
              }
            });
            Thread t2 = new Thread(new Runnable() {			
              @Override
              public void run() {				
                c.deposit(600);
              }
            });
            t1.start();
            // inject delay to allow t1 to hit withdraw
            try {
              Thread.sleep(2000);
            } catch(InterruptedException e) {			
            }
            t2.start();
          }
        }

            /*
                output :
                1000: rupees not sufficient, waiting for balance.
                600 rupees creadited to account.
                amount 600 rupees deposited.
                remaining balance : 100

            */
