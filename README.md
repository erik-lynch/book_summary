# book_summary
Microservice that receives a book title, and returns the summary provided on the book's wikipedia entry.

=========HOW TO REQUEST:========

This microservice uses zmq as the communication pipeline. In order to make a request, you will need to import zmq in your python file:

import zmq

To connect to the server, use the following code:

context = zmq.Context()

#  Socket to talk to server
socket = context.socket(zmq.REQ)
socket.connect("tcp://192.168.50.37:5555")

To make a request send the book title as a string:

#  Send book title to search
socket.send_string("BOOK TITLE GOES HERE")

========HOW TO RECEIVE:========

To receive and format the response, insert the following code:

#  Get the reply, and format
message = socket.recv()
message = str(message)
message = message[2:-1]

That's all! You may use the summary in any way you need once it has been stored in a variable. 
