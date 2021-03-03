An interrupt is an indication to a thread that it should stop what it is doing and do something else. 
It's up to the programmer to decide exactly how a thread responds to an interrupt.



        Thread t1 = new Thread(new Runnable() {

              @Override
              public void run() {
                // TODO Auto-generated method stub
                try {
                  Thread.sleep(5000);
                } catch(InterruptedException e) {
                  System.out.println("thread interrupted");
                  // do something else code called here
                }
              }
            });

            t1.start();
            t1.interrupt();
