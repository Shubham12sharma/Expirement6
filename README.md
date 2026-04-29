Title

Mutual Exclusion Algorithm using Java

🔹 Aim

To demonstrate mutual exclusion using a simple Java program.

🔹 Theory (Short & Exam-Oriented)

Mutual exclusion is a key concept in concurrent and distributed systems that ensures that only one process or thread can access a shared resource (critical section) at any given time. This is necessary to prevent race conditions, where multiple threads try to modify shared data simultaneously, leading to incorrect results.

🔸 Critical Section Problem

A program is divided into:

Entry Section – Code to request access
Critical Section – Shared resource access
Exit Section – Release resource
Remainder Section – बाकी code
🔸 Requirements of Mutual Exclusion

For a correct solution, three conditions must be satisfied:

Mutual Exclusion
Only one process can be in the critical section at a time.
Progress
If no process is in the critical section, one of the waiting processes should be allowed to enter.
Bounded Waiting
A process should not wait indefinitely (no starvation).
🔸 Methods to Achieve Mutual Exclusion
Software Solutions
Peterson’s Algorithm
Dekker’s Algorithm
Hardware Solutions
Test-and-Set instruction
Compare-and-Swap
High-Level Language Support (Java)
synchronized keyword
Locks (ReentrantLock)
Semaphores

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
