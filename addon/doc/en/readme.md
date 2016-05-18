#NVDA Remote Access
Version 1.3.1, Unofficial fork by [Blake Oliver](https://github.com/oliver2213)
##Please Note
This is an unofficial fork of the [NVDA Remote add-on](https://github.com/NVDARemote/NVDARemote). This probably doesn't mean much, the code is still open source and hosted on Git hub, [right here](https://github.com/oliver2213/NVDARemote).
This does mean, however, that I don't have updated translations for the documentation that I change. If you can help with this, then feel free to email me at oliver22213@me.com, or clone the git repository linked above, update any translations you can, then [file a pull request](https://github.com/oliver2213/nvdaremote/pulls) and I'll gladly add your translation.  
If you find any bugs with this add on, and you believe it relates to my changes, feel free to [create an issue on Git hub](https://github.com/oliver2213/nvdaremote/issues), and I'll try to fix it. If you find a bug in what you believe to be the NVDA Remote add-on itself, you can always [file an issue to the official repository](https://github.com/NVDARemote/nvdaremote/issues),. I merge in upstream changes from the official repository into this fork, so if they implement it, and you stay up to date, you'll get it.

#Introduction
Welcome to the NVDA Remote Access addon, which will allow you to connect to another computer running the free NVDA screen reader. It makes no difference whether you are across the room or across the world. Connecting is simple, and there are very few commands to remember. You can connect to another person's computer, or allow a trusted person to connect to your system to perform routine maintenance, diagnose a problem, or provide training.

##Before You Begin

You will need to have installed NVDA on both computers, and obtain the NVDA Remote Access addon.
The installation of both NVDA and the Remote Access addon are standard. If you need more information, this can be found in NVDA's User Guide.

##Starting a remote session through a relay server
###Controlled	 computer
1. Open the NVDA menu, Tools, Remote, Connect.
2. Choose client in the first radio button.
3. Select Allow this machine to be controlled in the second set of radio buttons.
4. In the host field, enter the host of the server you are connecting to, for example nvdaremote.com.
5. Enter a key into the key field, or press the generate key button.
The key is what others will use to control your computer.
The machine being controlled and all its clients need to use the same key.
6. Press ok. Once done, you will hear a tone and connected.

###Controlling computer
1. Open the NVDA menu, Tools, Remote, Connect.
2. Choose client in the first radio button.
3. Select Control another machine in the second set of radio buttons.
4. In the host field, enter the host of the server you are connecting to, for example nvdaremote.com.
5. Enter a key into the key field, or press the generate key button.
The machine being controlled and all its clients need to use the same key.
6. Press ok. Once done, you will hear a tone and connected.

##Direct connections
The server option in the connect dialog allows you to set up a direct connection.
Once selecting this, select which mode your end of the connection wwill be in.
The other pperson will connect to you using the opposite.

Once the mode is selected, you can use the Get External IP button to get your external IP address and
make sure the port is forwarded correctly.
If portcheck detects that your port (6837) is not reachable, a warning will appear.
Forward your port and try again.
Note: The process for forwarding ports is outside of the scope of this document. Please consult the information provided with your router for further instruction.

Enter a key into the key field, or press generate. The other person will need your external IP along with the key to connect.

Once ok is pressed, you will be connected.
When the other person connects, you can use NVDA Remote normally.

##Gestures and hotkeys (this fork only!)
You can asign custom gestures / hotkeys to most NVDA Remote actions for quicker use of these features. To add, remove, and modify these bindings, do the following:

1. Open the NVDA menu > preffrences > input gestures.
2. In the tree view that appears, arrow down to NVDA Remote and expand it with right arrow.
3. For each action you would like a gesture / hotkey for, select it in the tree view, tab to the add button, then perform the gesture /hotkey. Once done, choose what keyboard layout it should bind to in the menu that appears and hit enter.
4. Repeat for all actions you'd like. You can remove a binding by finding it inside an action's tree view and tabbing to the remove button.
5. When done, press ok. Your bindings should take effect immediately.

##Sending keys
Once the session is connected, the controlling machine can then press f11 to start sending keys.
When NVDA says sending keys, the keys you press will go to the remote machine. Press f11 again to stop sending keys and switch back to the controlling machine.
For best compatibility, please ensure that the keyboard layouts on both machines match.

##Send Ctrl+Alt+Del
While sending keys, it is not possible to send the CTRL+Alt+del combination normally.
If you need to send CTRL+Alt+del, and the remote system is on the secure desktop, use this command.

##Remotely Controlling an Unattended Computer

Sometimes, you may wish to control one of your own computers remotely. This is especially helpful if you are traveling, and you wish to control your home PC from your laptop. Or, you may want to control a computer in one room of your house while sitting outside with another PC. A little advanced preparation makes this convenient and possible.  

There are 2 methods to do this:
###Method 1: Using an automatic self-hosted server (this is a feature of this fork only!):

1. Navigate to the NVDA menu > Tools > Remote > options.
2. In the first radiobutton selection box, arrow down until you get to "Autoconnect to a self-hosted server ".
3. Tab once, over to the "key" text field. Since this server will automatically be started when NVDA (or the add-on itself) starts, you can not choose to "randomly generate a key", as, when connecting from a remote computer, you would have no idea what said key was. Come up with a **unique** key that only you know and enter it here.
4. Press Ok.  

Now, when NVDA or the add-on starts up, it will automatically start a local NVDARemote server that you can connect to, just like a normal server, to control that computer. This has several advantages and disadvantages over the second method:
* You don't need to leave your computer constantly connected to a remote server that you most likely don't control which could potentially remotely control your computer.
* You don't have to worry about the relay server your using going down when you are away from the computer that you need to have remote access to - the server is hosted in the NVDA process itself.
* You will, however, need to forward TCP Port 6837 in your router if you intend to use this self-hosted server outside of your local network.

###Method 2: Connect to an external control server

1. Enter the NVDA menu, and choose Tools, then Remote. Finally, press Enter on Options.
2. Tab to the first radiobutton, and arrow until you get to "Autoconnect to an external control server "
3. Fill in the Host and Key fields, tab to OK, and press Enter.
4. Please note: the Generate Key option is not available in this situation. It is best to come up with a key you will remember so you can easily use it from any remote location.

While you won't need to open any ports through your router for this method to work, be aware that (essentially), you are leaving a connection open to a server that you most likely do not own or have any sort of control over. It would be relatively trivial for the operator of said server to see that your computer regularly connects to it, and to get the key it uses to do so, and hense gain complete control over your system. If this bothers you at all, don't worry. You can [run your own NVDA Remote server!](https://github.com/Technow-es/NVDARemoteServer)

##Muting Speech on the Remote Computer
If you do not wish to hear the remote computer's speech, simply access the NVDA menu, Tools, and Remote. Arrow down to Mute Remote Speech, and press Enter.


##Ending a remote Session

To end a remote session, do the following:

1. On the controlling computer, press F11 to stop sending keys. You should hear the message: "Not sending keys." If you instead hear a message that you are sending keys, press F11 once more.

2. Access the NVDA menu, then Tools, Remote, and press Enter on Disconnect.

##Push clipboard
The Push clipboard option in the remote menu allows you to push text from your clipboard.
when activated, any text on the clipboard will be pushed to the other machines.

##Configuring NVDA Remote to Work on a Secure Desktop

In order for NVDA Remote to work on the secure desktop, the addon must be installed in the NVDA running on the secure desktop.

1. From the NVDA menu, select Preferences, then General Settings.

2. Tab to the Use Currently Saved Settings on the Logon and Other Secure Screens (requires administrator privileges) button, and press Enter.

3. Answer Yes to the prompts regarding copying your settings and about copying plugins, and respond to the User Account Control prompt that may appear.
4. When settings are copied, press Enter to dismiss the OK button. Tab to OK and Enter once more to exit the dialog.

Once NVDA Remote is installed on the secure desktop, if you are currently being controlled in a remote session,
the secure desktop will read when switched to.

##Contributions
We would like to acknowledge the following contributors, among others, who helped make the NVDA Remote project a reality.

* Hai Nguyen Ly
* Chris Westbrook
* Thomas Huebner
* John F Crosotn III
* Darrell Shandrow
* D Williams
* Matthew McCubbin
* Jason Meddaugh
* ABDULAZIZ ALSHMASI.
* Tyler W Kavanaugh
* Casey Mathews
