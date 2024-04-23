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
the code itself is being executed from and "5672" refers to the port number from which the broker is listening from. Therefore,
"localhost:5672" would mean that the code will be run locally from the machine, accessible through the port 5672.
