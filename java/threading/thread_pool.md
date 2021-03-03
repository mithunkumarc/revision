Java Thread pool represents a group of worker threads that are waiting for the job and reuse many times.

In case of thread pool, a group of fixed size threads are created. 
A thread from the thread pool is pulled out and assigned a job by the service provider. 
After completion of the job, thread is contained in the thread pool again.

#### Advantage of Java Thread Pool

Better performance It saves time because there is no need to create new thread.

#### Real time usage

It is used in Servlet and JSP where container creates a thread pool to process the request.


#### implemnetation

1. set the size of pool

        ExecutorService executor = Executors.newFixedThreadPool(5);//creating a pool of 5 threads  

2. create your thread class/runnable class

        class MyRunnable implements Runnable {
              public void run(){
                  // task
              }
        }
        Thread t1 = new Thread(new MyRunnable);

3. Ask executer to run thread using thread pool(thread already avaialble)


         executor.execute(t1);
         executor.execute(t2);
         executor.execute(t3);
         ...
