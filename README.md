Title

Mutual Exclusion Algorithm using Java

🔹 Aim

To demonstrate mutual exclusion using a simple Java program.

🔹 Theory (Short & Exam-Oriented)

Mutual exclusion is a fundamental concept in concurrent programming where multiple processes/threads share a common resource. It ensures that only one process enters the critical section at a time, preventing data inconsistency and race conditions.

In Java, mutual exclusion can be achieved using:

synchronized keyword
Locks (like ReentrantLock)

In this program, we use the synchronized method, which allows only one thread to execute the critical section at a time.


class SharedResource {
    public synchronized void printNumbers(String threadName) {
        for (int i = 1; i <= 5; i++) {
            System.out.println(threadName + " -> " + i);
            try {
                Thread.sleep(500); // simulate work
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}

class MyThread extends Thread {
    SharedResource resource;

    MyThread(SharedResource resource) {
        this.resource = resource;
    }

    public void run() {
        resource.printNumbers(Thread.currentThread().getName());
    }
}

public class Main {
    public static void main(String[] args) {
        SharedResource resource = new SharedResource();

        MyThread t1 = new MyThread(resource);
        MyThread t2 = new MyThread(resource);

        t1.setName("Thread-1");
        t2.setName("Thread-2");

        t1.start();
        t2.start();
    }
}


🔹 Conclusion

The program demonstrates mutual exclusion using the synchronized method, ensuring that only one thread accesses the shared resource at a time, avoiding race conditions.
