# WifiBruteForcer
An active attack tool against Wi-Fi networks with internal CMD commands.

This program is created to be a proof of concept that it is possible to write a working Wi-Fi attack tool with Batchfiles since there are countless examples on the internet that claims to be legit hacking tools, working on CMD. While this tool does not claim a 100% success ratio, it still works if the target Wi-Fi has weak password. :)

## Commands
```txt
Commands

 - help             : Displays this page
 - wordlist         : Provide a wordlist file     
 - scan             : Performs a WI-FI scan       
 - interface        : Open Interface Management   
 - attack           : Attacks selected WI-FI      
 - counter          : Sets the attack counter     
 - exit             : Close the program
```

## Usage

### Interface initialization
The program automatically detects your wireless interfaces when you execute the batch file.
If it finds only one, it will select it as default. If there are multiple interfaces,
the program will ask you to choose one. If none exist, it will stay "not_defined".

> You can later change the interface by typing `interface` on the main menu.
> This will bring the interface initialization screen back.

### Scan
When you type `scan` at the main menu, the program will enumerate all Wi-Fi networks
available from the selected wireless interface. You can choose one by typing the number
associated with an SSID.

> No Name could mean that the network is hidden. You cannot attack that network.

> Performing a scan disconnects the interface from the network that it has connected previously.

### Selecting a wordlist
A wordlist file is already provided in the repository. If you want to use a custom
wordlist, you have to specify the file you are going to use by typing `wordlist` on the 
main menu and then typing the absolute or relative path of the wordlist file.

### Attacking
Simply type `attack` and the program will show you a warning screen that this process is going
to delete the profile associated with the SSID if you have connected to it before.
It means you will lose the password you entered while connecting to that SSID before.
Save it before using the attack.

### Counter
When a connection is attempted with `netsh` to a network, it takes time to establish the connection. To check whether the connection is successful,
the program repeatedly queries the connection status of the selected interface. A counter value controls how many times this query will be done.
If not changed, the counter value is 5, and counts down after each query for each password combination. 

> If an authentication or association is detected, this value is increased by 5 to ensure a successful connection.

## Limitations
- If connected to Network, its profile will be deleted.

- Low signal strength may cause false negatives.

- This app might not find the correct password if the signal strength is too low.

- Remember, this is an online attack. Expect slow attempts.

## Result file
If an attack is successful, the result is automatically written to `result.txt`.


## How its works?
- If you try with your network it will disconnect the network from your device and then try to connect with the passwords from the wordlist if it is connected then it will display success message.

- You can also try with the avaliable network, first you need to use `scan` command then you need to set the target and exploit the network.

- Use only for ethical purpose don't use for unethical activities.

## Legal Disclaimer

This tool is intended for ethical use only. Unauthorized access to Wi-Fi networks is illegal and unethical. Use this tool only to recover passwords for networks you own or have explicit permission to access.
