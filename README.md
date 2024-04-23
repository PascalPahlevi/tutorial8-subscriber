# Subscriber Reflection

a. What is amqp? <br>

AMQP, otherwise known as Advanced Message Queueing Protocol, is a message protocol that was specifically designed for
asynchronous messaging between applications and services. This message protocol allows the communication in distributed systems 
through its allowance of sending and receiving messages asynchronously across various different platforms and programming languages.

b. what it means? guest:guest@localhost:5672 , what is the first guest, and what is the second guest, and what is localhost:5672 is for? <br>

To begin with, the string "guest:guest@localhosts:5672" acts a connection URI in order to allow a connection with an AMQP
broker. The first "guest" in the string represents the username alongside the second "guest" which represents the password. Therefore,
putting the two together, "guest:guest" would refer to the username and password that is used when authenticating the 
connection with the AMQP broker. Moreover, "localhost" means that the broker would be running on the same maching wherein
the code itself is being executed from and "5672" refers to the port number from which the broker is listening from. Therefore, "localhost:5672" would mean that the code will be run locally from the machine, accessible through the port 5672.

# Slow Subscriber Simulation Screenshot
<img width="637" alt="image" src="https://github.com/PascalPahlevi/tutorial8-subscriber/assets/143638456/a5f199de-48cb-40e7-a563-1fed96934a67">
<img width="639" alt="image" src="https://github.com/PascalPahlevi/tutorial8-subscriber/assets/143638456/ba3b678e-df63-4b9c-b665-2c0bc910035c">

On my machine, the total number of queues was about 16. The total amount of messasges that was sent over by publisher was 20 
 (5 x 4) due to the fact that I ran it 4 times through `cargo run. In this case however, due to the addition of `thread::sleep(ten_millis);` in the subscriber code, a delay of ten milliseconds was made to happen in whichc case simulates a slow subcriber state causing the queue 0f 16 throughout the time period.

# Running three subscribers screenshot
<img width="640" alt="image" src="https://github.com/PascalPahlevi/tutorial8-subscriber/assets/143638456/ecdb5b6c-932c-41b0-be8a-03b39fcfa7b6">
<img width="639" alt="image" src="https://github.com/PascalPahlevi/tutorial8-subscriber/assets/143638456/85b66a3b-f527-4ad5-a434-debfd70efbe7">

As seen on the images above, the total number of queues went down by a significant amount, originally from 16 all the way to 4. Through the use of running three separate instances of subscriber, multithreading is eventually done as the multiple messages sent by the publisher is received by all three publishers at the same time thus ultimately reducing the overall load. Due to multithreading, the overall performance of the messages sent by the publisher and received by the subscriber is improved.

One way I can see on improving the performance of the subscriber and publisher codes is to implement asynchronous programming. This way it would improve the overall performance through concurrency allowing the messages to be sent and received conccurently.
