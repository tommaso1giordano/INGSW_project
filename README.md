# Software Engineering Project - AA 2022-2023

The project consists in the digital implementation of a board game called MyShelfie
engineered by:
- [Frazzei Simone](https://github.com/BurnoutBear)
- [Giordano Tommaso](https://github.com/tommaso1giordano)
- [Maffei Valentina](https://github.com/valem4ff)
- [Olivieri Luca](https://github.com/Luca-Olivieri)

The application runs on a single server able to connect to multiple clients over the same network. This way, the game can manage multiple players who can play as many matches as the want.

## Documentation:

### Architecture

The software has been design following the **MVC** architectural pattern (Model-View-Controller) in a Java development environment 

### Networking

Networking capabilities are allowed through **sockets** and **RMI** (Remote Method Invocation) in a client-server framework.

### Interface

The app has a **CLI**/**TUI** (Command Line Interface/Terminal User Interface) as well as a **GUI** (Graphical User interface) developed with JavaFX and designed with SceneBuilder.

### Project management

The code documentation has been written with **JavaDoc** conventions, the Java files building has been managed by **Maven** (a building automation tool) and the testing has been conducted through **JUnit**.

### Summary

| Functionality | Implementation |
| --- | ----------- |
| **Network (C-S)** | socket, RMI |
| **Interface** | CLI, GUI |
| **Code Doc** | JavaDoc |
| **Building** | Maven |
| **Testing** | JUnit |

### Game functionalities

The software logic covers every rule and aspect of the original game logic (**Regole complete**)
along with two advanced functionalities:
- **Partite multiple**: the server is able handle multiple matches and the players can play multiple matches as well.
- **Chat**: Players in the same match are able to chat with each other through a public and a private chat, which is match-exclusive.


## Usage

The software consists of two .jar files (downloadable [here](/deliverables/final/jar)), one for the server and one for the client. They are standalone files as they comprehend the GUI assets as well (unlike the source code posted on this repo) and they require JavaSE installed on the machine meant to run them.

### Server

The first .jar to run is the server one. The user can do it by opening the Terminal into the folder containing such file and typing this:
```
java -jar myshelfie-server.jar
```

By default, the server uses port 42000 for sockets and 42001 for RMI, while the IP address is the local IP of the computer running the server (for private connections).

If the user wishes to use custom ports, the former code has be completed with a specific flag:
```
java -jar myshelfie-server.jar --port X Y
```
where X is the port for the socket, while Y is for RMI.
Both ports must be in the 1024 - 65535 range and if for any reason the flag is not set entirely correctly, then it is ignored and the default ports are used instead.

### Client

The second .jar to run is the client app. The user can do it by opening the Terminal into the folder containing such file and typing this:
```
java -jar myshelfie-client.jar
```

By default, the client app runs with CLI and uses a socket network interface.
To decide whether to switch between CLI and GUI as well as socket and RMI we can set ``--gui`` and ``--rmi`` flags like in the following example:
```
java -jar myshelfie-client.jar --rmi --gui
```
Such flags can be set in any order and are completely independent from each other.

### Have fun!
