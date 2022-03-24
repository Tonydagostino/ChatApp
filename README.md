Chatroom website project for csc543

The ChatApp is a simple chatroom wesbite in which users can log into an account and chat with
members in different rooms. The site is modeled based off memories of using AIM as a kid.

Functionalities include:
-Real-Time Chat
-Mention other users with @ symbol
-Multiple Rooms
-User Created Rooms
-Password Locked Rooms
-Basic User Accounts


STRUCTURE:

---------------------------------------------------------------------------
SERVER FILES:

fileServer.js:
-Reads and displays appropriate information from multiple file types.


app.js:
-Create HTTP server and handle routing
-Listen for requests on port 80
-Utilizes socket.io to listen for client requests such as:
	-send chat message
	-change chatroom
	-create new chatroom
	-disconnect from site
-Utilizes AJAX to receive login and registration information from clients


chat.js:
-Handles events that occur within the chatroom
-Updates the front end to display messages and users
-Utilizes socket.io to send requests mentioned above


database.js:
-Utilizes mysql package for node.js
-Establish connection to the database
-Houses functions to query the database
----------------------------------------------------------------------------

CLIENT FILES:

clientLogin.js:
-Handles login and registration for the client
-Sends information to the server to be processed
-Utilizes AJAX to send information
-Event Handlers for login and register buttons
-Reroutes users to chat.html upon succesful login


clientSocket.js:
-Utilizes socket.io for sending and receiving requests
-Handles all client functions while in the chatrooms
----------------------------------------------------------------------------

Database:
Since we are utilizing Google Cloud to deploy the HTTP server, we concluded it would be best
to also use Google Cloud to create a database instance. The database holds our users' account
information, as well as custom created room instances.

Tables:
user: userID {PK}, username, password
room: roomID {PK}, roomName, password


