# Book Summary
Microservice that receives a book title, and returns the summary provided on the book's wikipedia entry. The microservice pulls the book summary using Wikipedia's API.

Allows for the quick retrieval of a book summary using only the book's title. 

# =========HOW TO REQUEST:========

This microservice uses zmq as the communication pipeline. In order to make a request, you will need to import zmq in your python file:

import zmq

To connect to the server, use the following code:

context = zmq.Context()

socket = context.socket(zmq.REQ)

socket.connect("tcp://192.168.50.37:5555")

To make a request send the book title as a string:

socket.send_string("BOOK TITLE GOES HERE")

# ========HOW TO RECEIVE:========

To receive and format the response, insert the following code:

message = socket.recv()

message = str(message)

message = message[2:-1]

That's all! You may use the summary in any way you need once it has been stored in a variable. 

<img width="1057" alt="image" src="https://user-images.githubusercontent.com/114192977/199138213-a7e2f25a-4a3e-45c4-a5f1-bb628a9ad64d.png">

This program was written by and is maintained by Erik Lynch
