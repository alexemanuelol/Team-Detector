# Team-Detector
A program that detect teams on games available at Battlemetrics and Steam by comparing names in Battlemetrics player list and suspect friend list.

# Clone and Setup
To clone the repository:
	$ git clone https://github.com/alexemanuelol/Team-Detector.git

Install the required packages:
``` bash
$ cd Team-Detector
$ pip install -r requirements.txt
```

# Usage
You provide the program with two links:
- The URL of the Battlemetrics Server Page that you're playing on (-b flag).
- The Steam Profile of the player you want to inspect (-s flag).

The program goes through the player list on the battlemetrics server page and saves all player names in an array. Then it goes through the Steam friend list of the player you want to inspect and compares the friend list names with the Battlemetrics player array to find out which friends are currently on the server. If the program found any matches, it will then continue to go through the friend list of those friends and so on. What you end up with is a table of all the players that might be part of the same team as the player you provided the Steam Profile. It will also create a .html file that visualize the friends network to see who is friends with who etc...

![Image of the command output for a Rust Server](images/command_image.png)

![Image of the network](images/network_image.png)

You can download the windows executable from [releases](https://github.com/alexemanuelol/Team-Detector/releases) page and run the .exe file like so:

```bash
$ teamDetector.exe -b https://battlemetrics.com/servers/GAME/XXXXX -s https://steamcommunity.com/profiles/XXXXXXXXXXXXXXXXX
```

# Notes
The program will only find players that are currently online on the server that is displayed in the Battlemetrics Server Page. If the server have streamer mode on, this program won't work. Also, if you try to run the script on a person that have the friend list private, this program won't work.