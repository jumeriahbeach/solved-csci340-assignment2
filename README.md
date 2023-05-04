Download Link: https://assignmentchef.com/product/solved-csci340-assignment2
<br>
Build a program which schedules simulated processes.




<strong>Design: </strong>




<ol>

 <li>The simulator implements three different CPU scheduling algorithms. The simulator selects a process to run from the ready queue based on the scheduling algorithm chosen at runtime.  Since the assignment intends to simulate a CPU scheduler, it does not require any actual process creation or execution.  When the CPU scheduler chooses the next process, the simulator will simply print out which the process selected to run at that time.  The simulator output is like a Gantt chart.</li>

</ol>




<ol start="2">

 <li>A <strong>Process</strong> is an object in this assignment storing integers which are its ID, arrival time, and CPU burst length. Another object in this assignment is the <strong>Scheduler</strong> which simulates the CPU scheduler for an operating system, the one chosen at runtime.  The scheduler contains the ready queue and the only operations the scheduler performs is add and remove.  The add operation adds a process into the ready queue into its appropriate spot within the ready queue according to the CPU scheduling algorithm, the one chosen at runtime.  The remove operation removes a process from the ready queue according to the CPU scheduling algorithm, the one chosen at runtime.  The scheduler implements the CPU scheduling algorithms: First Come First Serve, Shortest Remaining Time First which is the preemptive version of Shortest Job First, and Round Robin.</li>

</ol>




<ol start="3">

 <li>Create a driver class and make the name of the driver class <strong>Assignment2</strong> and it should only contain only one method: public static void main(String args[]).</li>

</ol>

The main method receives, via the command line arguments, the name of the CPU scheduler that your simulator program will use.  If Round Robin is the CPU scheduler chosen, then the main method also receives the time quantum value via an additional command line argument.  The main method opens the file <strong>assignment2.txt</strong> reading in the entire set of processes and initiates execution of the simulator program.  Assume there is only a single processor with only one core.  The main method itself should be fairly short.




The command to launch the program using First Come First Serve scheduling: java Assignment2 FCFS




The command to launch the program using Shortest Remaining Time First scheduling: java Assignment2 SRTF




The command to launch the program using Round Robin scheduling with a time quantum of 10: java Assignment2 RR 10







<ol start="4">

 <li>The input to the program reads from a plain text file called <strong>txt</strong>. This is the statement to use to open the file:</li>

</ol>




FileInputStream fstream = new FileInputStream(“assignment2.txt”);




Assuming you are using Eclipse to create your project, you will store the input file assignment2.txt in the parent directory of your source code (<strong>.java</strong> files) which happens to be the main directory of your project in Eclipse.  If you are using some other development environment, then you have to figure out where to store the input file.




Each line in the file represents a process, 3 integers separated by a space or spaces.  The process information includes the process ID, arrival time, and CPU burst length.  Arrival time is the time at which the scheduler receives the process and places it in the ready queue.  You can assume arrival times of the processes in the input file are in non-decreasing order.  Process IDs are unique.  Arrival times may be duplicated, which means multiple processes may arrive at the same time.  The following table is an example of a three process input file.  The text in the top row of the table is just to label the value in each column and would not appear in the input file.  Remember, a space or spaces separate the integers on each line.




<table width="384">

 <tbody>

  <tr>

   <td width="115">Process ID</td>

   <td width="115">Arrival Time</td>

   <td width="154">CPU Burst Length</td>

  </tr>

  <tr>

   <td width="115">1</td>

   <td width="115">0</td>

   <td width="154">10</td>

  </tr>

  <tr>

   <td width="115">2</td>

   <td width="115">0</td>

   <td width="154">20</td>

  </tr>

  <tr>

   <td width="115">3</td>

   <td width="115">3</td>

   <td width="154">5</td>

  </tr>

 </tbody>

</table>




<ol start="5">

 <li>For the output, the example below best describes what the program should produce. The program will not be tested on this sample input but a different sample input.</li>

</ol>




Here is the example input:




<ul>

 <li>0 10</li>

 <li>0 9</li>

 <li>3 5</li>

 <li>7 4</li>

 <li>10 6</li>

 <li>10 7</li>

</ul>




Here is the output produced for the above example input given the command java Assignment2 FCFS to execute the program:




Scheduling algorithm: First Come First Serve

============================================================

&lt;system time    0&gt; process    1 is running

&lt;system time    1&gt; process    1 is running

&lt;system time    2&gt; process    1 is running

&lt;system time    3&gt; process    1 is running

&lt;system time    4&gt; process    1 is running

&lt;system time    5&gt; process    1 is running

&lt;system time    6&gt; process    1 is running

&lt;system time    7&gt; process    1 is running

&lt;system time    8&gt; process    1 is running

&lt;system time    9&gt; process    1 is running &lt;system time   10&gt; process    1 is finished….

&lt;system time   10&gt; process    2 is running

&lt;system time   11&gt; process    2 is running

&lt;system time   12&gt; process    2 is running

&lt;system time   13&gt; process    2 is running

&lt;system time   14&gt; process    2 is running

&lt;system time   15&gt; process    2 is running

&lt;system time   16&gt; process    2 is running

&lt;system time   17&gt; process    2 is running

&lt;system time   18&gt; process    2 is running &lt;system time   19&gt; process    2 is finished….

&lt;system time   19&gt; process    3 is running

&lt;system time   20&gt; process    3 is running

&lt;system time   21&gt; process    3 is running

&lt;system time   22&gt; process    3 is running

&lt;system time   23&gt; process    3 is running &lt;system time   24&gt; process    3 is finished….

&lt;system time   24&gt; process    4 is running

&lt;system time   25&gt; process    4 is running

&lt;system time   26&gt; process    4 is running

&lt;system time   27&gt; process    4 is running &lt;system time   28&gt; process    4 is finished….

&lt;system time   28&gt; process    5 is running

&lt;system time   29&gt; process    5 is running

&lt;system time   30&gt; process    5 is running

&lt;system time   31&gt; process    5 is running

&lt;system time   32&gt; process    5 is running

&lt;system time   33&gt; process    5 is running &lt;system time   34&gt; process    5 is finished….

&lt;system time   34&gt; process    6 is running

&lt;system time   35&gt; process    6 is running

&lt;system time   36&gt; process    6 is running

&lt;system time   37&gt; process    6 is running

&lt;system time   38&gt; process    6 is running

&lt;system time   39&gt; process    6 is running

&lt;system time   40&gt; process    6 is running

&lt;system time   41&gt; process    6 is finished….

&lt;system time   41&gt; All processes finished……

============================================================

Average CPU usage:       100.00%

Average waiting time:     14.17

Average response time:    14.17

Average turnaround time:  21.00

============================================================







<ol start="6">

 <li>You must declare public each class you create which means you define each class in its own file.</li>

</ol>




<ol start="7">

 <li>You must declare private all the data members in every class you create.</li>

</ol>




<ol start="8">

 <li>It is possible to use inheritance in this assignment, extends one class in another class. But, it has to be the proper use of inheritance.  If you simply use extends in one class to allow it access to the private data members of another class and the two classes do not have similar behavior, then that is not the proper use of inheritance.  Improper use of inheritance will cause a loss in points.</li>

</ol>




<ol start="9">

 <li><strong>Tip:</strong> Make your program as modular as possible, not placing all your code in one .java file. You can create as many classes as you need in addition to the class described above.  Methods being reasonably small follow the guidance that “A function does one thing and does it well.”  You will lose a lot of points for code readability if you do not make your program as modular as possible.  But do not go overboard on creating classes and methods.  Your common sense guides your creation of classes and methods.</li>

</ol>




<ol start="10">

 <li>Do <strong>NOT</strong> use your own packages in your program. If you see the keyword <strong>package</strong> on the top line of any of your .java files, then you created a package.  Create every .java file in the <strong>src</strong> folder of your Eclipse project, if you’re using Eclipse.</li>

</ol>




<ol start="11">

 <li>Do <strong>NOT</strong> use any graphical user interface code in your program!</li>

</ol>




<ol start="12">

 <li>Do <strong>NOT</strong> type any comments in your program. If you do a good job of programming by following the advice in number 9 above, then it will be easy for me to determine the task of your code.</li>

</ol>


