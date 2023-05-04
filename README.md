Download Link: https://assignmentchef.com/product/solved-csc230-exercise-20-echo-server-in-tcp-and-udp
<br>
For this program, you are going to implement an echo server in TCP and UDP, and compare their behaviors.   An echo server reads or receives what the client sends, and simply echoes or sends it back to the client.  This demonstrates that a connection is established properly, and that sending and receiving work, but isn’t useful for anything else.




You have been given the code for an echo TCP server (both sequential and concurrent) on the class Moodle site, under Lecture 20.  Modify the <strong>unitcp-client</strong> code to output only what is sent back to it by the server, then run the server and client on a port number specified as a command line argument for both programs.  Following this, run <strong>diff</strong> to compare the input read in by the client, and the output produced by the client, which should, if all things work, be the same.




For instance, in one terminal window, run: <strong>echotcp-server 9999 </strong>




And in another window, run:

<h3>unitcp-client 127.0.0.1 9999 &lt; &lt;testfile.txt&gt; &gt; tcpout.txt diff &lt;testfile.txt&gt; tcpout.txt</h3>

where <strong>&lt;testfile.txt&gt;</strong> is any file you wish to use for testing.  Provided for this exercise are several files for testing.  The result of the diff should be that there are no differences between the file contents sent by the client, and the file contents output by the client, after being echo’d by the server.




You can also run the server in the background, which will not require you to use separate terminal windows.  To do so, enter:

<h3>echotcp-server 9999 &amp;</h3>




(i.e., the trailing &amp; indicates to run the job in the background). At any time, to terminate a running process which is running in the foreground, type Ctrl-C.  To terminate a running background process, send it a SIGKILL signal, as follows: <strong>kill -9 echotcp-server </strong>







<h2>Part 2</h2>

You also have two UDP servers (both sequential) given to you.  Modify one of these to read input from a client and and simply echo it back, similar to the echotcp-server, but using the functions for reading and writing that are specific to UDP.  Name this program echoudpserver.c.




Then in one terminal window, run:

<strong>echoudp-server 8888 </strong>




And in another window, run:

<h3>uniudp-client 127.0.0.1 8888 &lt; &lt;testfile.txt&gt; &gt; udpout.txt diff &lt;testfile.txt&gt; udpout.txt</h3>

Try this with at least the sample input files provided with this exercise.  Are the input file and the output file always the same?  Remember, UDP is not reliable delivery.







<h2>Part 3</h2>

Lastly, modify the echotcp-concurrent server so that after reading input from the client, followed by an indication there is no more input, the server “sleeps” (suspends execution) for 30 seconds (using the <strong>sleep(30)</strong> function call) before echoing the input back to the client.

Then in 3 separate windows run:

<h3>echotcp-concurrent 7777</h3>

and

<strong>unitcp-client 127.0.0.1 7777 &lt; &lt;testfile.txt&gt; &gt; tcpout1.txt </strong>

and

<strong>unitcp-client 127.0.0.1 7777 &lt; &lt;testfile.txt&gt; &gt; tcpout2.txt </strong>




Or run these as 3 separate background processes.




Start the execution of the two clients closely in time, so their execution overlaps.  Does the server handle concurrent requests properly?







<h1>Submitting Your Work</h1>




When you’re done, submit your completed echotcp-server.c, echotcp-concurrent.c, unitcpclient.c, echoudp-server.c, and uniudp-client.c files to Exercise 20 in Moodle.





