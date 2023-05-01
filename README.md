Download Link: https://assignmentchef.com/product/solved-cgs3763-programming-project-1-concurrency-semaphores
<br>



1.- In this assignment you will implement a deadlock free variant of the bounded-buffer producer/consumer using jBACI (C – -). C- – is a subset of C + + that allows you to declare semaphores and apply the operations P and V.

In the standard solution with one producer and one consumer, you will need at least three semaphores named:

<ol>

 <li>Full – to stop the producer from producing items when the buffer is full. (initial value n= buffer size)</li>

 <li>Empty – to stop the consumer from consuming items from the buffer when the buffer is empty (initial value zero)</li>

 <li>Mutex – to allow only one process in the critical section (initial value one)</li>

</ol>




In this variant of the producer/consumer, there will be one producer (P), one Consumer (C) and one buffer; the size of the buffer is 5.

The producer will produce 20 items and stop running.

The consumer will consume items from the buffer until the 20 items have been consumed

<strong> </strong>

<strong>Project Direction </strong>

You will write the program based on the <strong>BACI</strong> interpreter. Download jBACI   executable files, example files, and documentation from




<strong><a href="https://code.google.com/p/jbaci/">http://code.google.com/p/jbaci/</a></strong>

<strong> </strong>

<strong><a href="http://www.weizmann.ac.il/sci-tea/benari/software/jbaci/index.html">http://www.weizmann.ac.il/sci-tea/benari/software/jbaci/index.html</a></strong>

<strong> </strong>

or you can access a document on the folder JBACI in Webcourses that tells you how to download and install  jBACI on your computer.

<em> </em>

The <strong>BACI</strong> support C– programming, which is a subset of C++ extended with primitives for process synchronization (Semaphores and Monitors).




Program example in BACI:




<strong>line pc</strong>

<strong>1 0 // example of C– semaphore usage</strong>

<strong>2 0</strong>

<strong>3 0 semaphore count; // a “general” semaphore</strong>

<strong>4 0 binarysem output; // a binary (0 or 1) semaphore for unscrambling output</strong>

<strong>5 0</strong>

<strong>6 0 void increment()</strong>

<strong>7 0 {</strong>

<strong>8 0 p(output); // obtain exclusive access to standard output</strong>

<strong>9 2 cout &lt;&lt; “before v(count) value of count is ” &lt;&lt; count &lt;&lt; endl;</strong>

<strong>10 6 v(output);</strong>

<strong>11 8 v(count); // increment the semaphore</strong>

<strong>12 10 } // increment</strong>

<strong>13 11</strong>

<strong>14 11 void decrement()</strong>

<strong>15 11 {</strong>

<strong>16 11 p(output); // obtain exclusive access to standard output</strong>

<strong>17 13 cout &lt;&lt; “before p(count) value of count is ” &lt;&lt; count &lt;&lt; endl;</strong>

<strong>18 17 v(output);</strong>

<strong>19 19 p(count); // decrement the semaphore (or stop — see manual text)</strong>

<strong>20 21 } // decrement</strong>

<strong>21 22</strong>

<strong>22 22 main()</strong>

<strong>23 23 {</strong>

<strong>24 23 initialsem(count,0);</strong>

<strong>25 26 initialsem(output,1);</strong>

<strong>26 29 cobegin {</strong>

<strong>27 30 decrement(); increment();</strong>

<strong>28 36 }</strong>

<strong>29 37 } // main</strong>










<strong>Test your solution</strong>




You must run and test your solution for two cases as explain below and compare and comment on the results emitted by each test:

<ol>

 <li>Test your first solution</li>

 <li>Introduce a time delay in the consumer and test your solution. Time delay can be implemented using a dummy loop that iterates, for example, 1000 times</li>

</ol>


