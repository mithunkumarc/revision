
Java provides a convenient way to group multiple threads in a single object.

use class ThreadGroup to group threads  

      ThreadGroup tg1 = new ThreadGroup("Group A");//group A : name of thread group   


Default thread group is Main thread group

      if a thread doesn't belong to any group, then it belong to main thread group
      
      Thread.currentThread().getThreadGroup();
      
#### example

        public class HelloWorld {
          public static void main(String[] args) {
            System.out.println("default thread group is main thread group");
            Thread t = new Thread(new Runnable() {

              @Override
              public void run() {
                // TODO Auto-generated method stub
                System.out.println(Thread.currentThread().getThreadGroup());
              }
            });
            t.start();


            //some delay
            try {Thread.sleep(1000);}catch(InterruptedException e) {}


            System.out.println("t1, t2 and t3 belong to transactions thread group");
            ThreadGroup threadGroup = new ThreadGroup("transactions");
            Thread t1 = new Thread(threadGroup, () -> System.out.println("t1 : "+Thread.currentThread().getThreadGroup()));
            Thread t2 = new Thread(threadGroup, () -> System.out.println("t2 : "+Thread.currentThread().getThreadGroup()));
            Thread t3 = new Thread(threadGroup, () -> System.out.println("t3 : "+Thread.currentThread().getThreadGroup()));
            t1.start();
            t2.start();
            t3.start();
          }
        }
