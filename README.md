# Count-It-First
# Networked Counting Game - "Count-It-First"
# CSC/CPE 4750
# Author: Tai Doan, Hung Nguyen, Huyen Nguyen

## 1. Features:
Server-client based  using TCP socket connection.

There are 2 servers always be running concurrently for 2 game modes Easy and Hard.

When starting the application, player is able to choose game mode.

	Mode Easy: Random number generated in range [10,30], add +1 or +2
	Mode Hard: Random number generated in range [30,50], add +1, +3 or +5
	
The game will start when 2 players connect to the same room (i.e. the server)

Players will be announced what the "Win number" is from the server. Each player will take turn to input a number and send it to the server, the number will be added up to the sum. Whoever reaches the generated number first will win the game.

## 2. GUI Features:
We use pyQT5 library to design GUI layer for the connection between server and client.

The GUI is for clients to see the game better so the server runs in the back-end does not need to have GUI.

There are 3 different pages:
  - HOME PAGE WINDOW (home.py)
    + GAME MODE - Easy button or Hard button.
    + QUIT - close the application.
  - EASY GAME WINDOW (easyWindow.py)
    + WIN NUMBER - Display random number generated by the server.
    + CURRENT NUMBER - Display current number after the server sends back the response.
    + BUTTONS - +1 or +2 depends on the player's choice.
    + GENERATE - give the player option to generate the number to play.
    + QUIT - close the game.
  - HARD GAME WINDOW (hardWindow.py)
    + WIN NUMBER - Display random number generated by the server.
    + CURRENT NUMBER - Display current number after the server sends back the response.
    + BUTTONS - +1, +3, +5 depends on the player's choice.
    + QUIT - close the game.
  
## 3. Installation:

- Run server: 
    - Change directory to the folder contains the server files (server-Easy.py or server-Hard.py)
    - IP-address (e.g. localhost)

```bash
python3   server-Easy.py   IP-address
```
Server Easy will run on Port 43500
	
```bash
python3   server-Hard.py   IP-address
```
Server Hard will run on Port 43505

Run client:
  - Before:
      + As GUI is designed by PyQt5, the computer needs to install PyQt5 application.
  
```bash
pip3   install   PyQt5
```
  - After:
      + Open two other command prompt windows (Terminal for Mac or Ubuntu/Command Prompt for Window)
      + Change directory to the folder contains the client file (home.py)
```bash
python3   home.py 
```
	(INSTRUCTION)
      + Home.py imports client.py, easyWindow.py, and hardWindow.py so when you run home.py they are all connected and works as a completed GUI.
      + Click GENERATE first to display the random number generated by the server.
      + Then, you play the game by click buttons (+1, +2) for EASY mode and (+1, +3, +5) for HARD mode.
      + When you are done w the game, it will show a label "YOU WIN" or "YOU LOSE" below the buttons.
      + QUIT when you want to start a new game or close the application.
			


