# cs-511-homework-assignment-2-solved
**TO GET THIS SOLUTION VISIT:** [CS 511: Homework Assignment 2 Solved](https://www.ankitcodinghub.com/product/cs-511-homework-assignment-2-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;105903&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;3&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (3 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS 511: Homework Assignment 2 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (3 votes)    </div>
    </div>
Problem Description

The bakery, as describe above, is illustrated in Figure 1. The green arrow depicts the access door to the bakery and the red arrow the exit door. Only one

Figure 1: Bakery

customer can remove a loaf from a shelf at a time. Only one customer can be at a register at a time.

2.1 The Bakery

The simulation of the bakery starts by spawning one thread executing the code in the method Bakery.run(). The file Assignment2.java is in charge of doing this. Below we describe the contents of the class Bakery. In this particular class, you will have to:

1. Complete the implementation of the method Bakery.run()

2. Declare any necessary semaphores

The Bakery class has the following fields and methods:

Bakery

private static final int TOTAL_CUSTOMERS = 200 private static final int CAPACITY = 50 private static final int FULL_BREAD = 20 private Map&lt;BreadType, Integer&gt; availableBread private ExecutorService executor private float sales

public void takeBread(BreadType bread) public void addSales(float value) public void run()

The bakery has a store capacity CAPACITY and a number of total customers TOTAL_CUSTOMERS that visit during the day. This last number will be used as the number of customers in the simulation of the bakery. The bakery has a stock of 20 loaves of each type of bread with a price given in the stub (see BreadType.java). Each type of bread is stocked on a different shelf that only one customer can access at a time. The current stock for each type of bread is held in the field Bakery.availableBread. The customers will pick between one and three random breads from the shelf. When they take an item from the shelf, it will be taken from the stock. In order for the customer to take from the shelf:

• The shelf must be available (i.e. not in “use” by another customer).

• The bread needs to be in stock.

After they get their bread, customers will proceed to one of the four cashiers and ‘buy’ the item which adds to the sales variable which is shared between the four cashiers. If all four cashiers are taken, the customer will have to wait their turn. The customer then graciously exits the bakery to let more customers in.

When a bread stock reaches 0 stock, the shelf restocks itself (the method

Bakery.takeBread(BreadType bread) provided in the stub does this). No one can access the shelf while it is being restocked. The available bread is stored in a ConcurrentHashMap, which is a thread-safe implementation of a HashMap, and assigned to the field Bakery.availableBread. We do not want to use the standard HashMap because its “get” and “put” operations are not atomic.

As mentioned above, the Bakery.takeBread method (supplied with the stub) takes an item off of the stock and handles the restocking process when necessary. Be sure to acquire the proper semaphore(s) before calling this operation.

2.2 Customer

This section describes the class Customer. In this particular class, you are asked to:

1. Implement the constructor Customer.Customer(Bakery bakery).

2. Implement the method Customer.run(). Note that each customer thread will be spawned by Bakery.run().

The Customer class has the following fields and methods:

Customer

private Bakery bakery private Random rnd private List&lt;BreadType&gt; shoppingCart private int shopTime private int checkoutTime

public Customer(Bakery bakery) public void run() public String toString() private boolean addItem(BreadType bread) private void fillShoppingCart() private float getItemsValue()

A customer has a shopping cart called shoppingCart that determines what bread they take. In addition, they also have a time they spend shopping and a time they spend at the cashier that is randomized. These random values are determined when a Customer is created.

The operation fillShoppingCart chooses what items the customers want to buy. The operation addItem takes the loaves from the respective shelves and puts it into the customers shopping cart (this operation is already implemented for you).

2.3 Solution

Model this scenario using semaphores. These semaphores must allow for a correct use of shared resources. The shared resources in this problem are:

• The shelves: a customer must wait to use the shelf if it is being used by another customer.

• The cashiers: declared in the bakery itself. There are four cashiers available in the bakery that the customers go to check out their items. If the cashiers are busy the customers have to wait until one of the cashiers is free.

• The sales: the sales variable is maintained by all cashiers and is updated when a customer checks out.

• The bakery itself is also a shared resource. However rather than using semaphore for upholding this requirement you are to use the maximum of TOTAL_CUSTOMERS as the size of your thread pool.

Regarding the simulation of the bakery, the bakery should generate customers randomly and have them do their shopping. Customers should have between one and three breads in their shopping list. The shopping itself should take some time but not too much (in the sense that the simulation doesn’t slow down too much). Also, the cashiers when checking out should take some time.

The simulation should print out events when a customer starts shopping, takes an item from stock, when it buys, and and then when it finishes. Each customer can be uniquely identified using its hashCode. After all customers have finished shopping, the program should print the total sales from the day before exiting using: System.out.printf(“Total sales = %.2fn”, sales);

2.4 List of Classes

Here is a list of the classes you have to define, all included in a package called

Assignment2

• Bakery

• BreadType

Is given in the stub and contains information about the bread and prices.

• Customer

Has a shopping cart that is randomly generated from the requirements above. Also needs a random value for the time spent shopping and also the time spent at checkout. Contains a method fillShoppingCart that generates what the customer wants from the shelves.

• Assignment2 – included in the stub. Starts the program.

1 /* start the simulation */ 2 public class Assignment2 {

3 public static void main(String[] args) {

4 Thread thread = new Thread(new Bakery()); 5 thread.start();

6

7 try {

8 thread.join();

9 } catch (InterruptedException e) {

10 e.printStackTrace();

11 }

12 }

13 }

2.5 A Note on Pool Threads and the Executor Interface

The Executor interface or its subinterface ExecutorService (which is the one we will be using in this assignment) represents an asynchronous execution mechanism which is capable of executing multiple tasks in the background. Such multiple tasks are referred to as thread pools. An Executor is normally used instead of explicitly creating threads for managing each of the tasks, i.e., rather than invoking new Thread(new(RunnableTask())).start() for each of a set of tasks, you might use:

1 Executor executor = anExecutor;

2 executor.execute(new RunnableTask1());

3 executor.execute(new RunnableTask2());

4 …

Thread pools are useful when we need to limit the number of threads running in an application at the same time as there is a performance overhead associated with starting a new thread (each thread is also allocated some memory for its stack, etcetera). Instead of starting a new thread for every task to execute concurrently, the task can be passed to a thread pool. As soon as the pool has any idle threads the task is assigned to one of them and is then executed.

There are many ways of managing thread pools. One easy way is to use the static method newFixedThreadPool of the class Executors (not to be confused with the Executor interface). This method, whose signature is

public static ExecutorService newFixedThreadPool(int nThreads)

Here is a simple example of ExecutorService:

1 ExecutorService executorService = Executors.newFixedThreadPool(10);

2

3 executorService.execute(new Runnable() {

4 public void run() {

5 System.out.println(“I am an asynchronous task!”);

6 }

7 });

8

9 executorService.shutdown(); Here is what is happening:

• An ExecutorService is created using the newFixedThreadPool(int) factory method. This creates a thread pool with 10 threads executing tasks.

• An anonymous class implementation of the Runnable interface is passed to the execute() method. This causes the Runnable to be executed by one of the threads in the ExecutorService.

3 SUBMISSION INSTRUCTIONS

• The ExecutorService is shut down, so the all threads finish running. To terminate the threads inside the ExecutorService you call its shutdown() method. The ExecutorService will not shut down immediately, but it will no longer accept new tasks, and once all threads have finished current tasks, it shuts down. All tasks submitted to the ExecutorService before shutdown() is called, are executed.

If you want to shut down the ExecutorService immediately, you can call the shutdownNow() method. This will attempt to stop all executing tasks right away, and skips all submitted but non-processed tasks. There are no guarantees given about the executing tasks. Perhaps they stop, perhaps the execute until the end. It is a best effort attempt.

In order to wait for all threads in the thread pool to finish after shutdown and, say, print the total sales for the client, you can use:

1 try {

2 executor.awaitTermination(1, TimeUnit.HOURS);

3 System.out.printf(“Total sales = %.2f “, sales);

4 } catch (InterruptedException ie) {

5 ie.printStackTrace();

6 }

7 }

3 Submission Instructions

Submit a zip file named Assignment2.zip through Canvas containing the java source files. Important: Please make sure that your assignment compiles before submitting.
