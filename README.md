#Unofficial NVDARemote fork
As stated above, this is my unofficial fork of [the original NVDA Remote addon ](https://github.com/NVDARemote/NVDARemote).  
Previously, I hadn't added a readme so it would be easier for developers on the original project to merge my pull requests, but as it seems they either have no intention of doing so, or will, but just "haven't gotten around to it yet", I've decided there is no reason why I should make one.
##So what does this "unofficial" fork of the addon do that the original doesn't?
Well...
* Adds gestures / hotkeys that you can set up yourself in NVDA's gesture's manager for:
  * Mute remote speech
  * connect (Open the dialog if a connection isn't already established)
  * Disconnect
  * Report addon status (I still need to work on this, don't be surprised if things don't report correctly)
  * Push clipboard
* ads a "automatic Self-hosted server" feature in the options dialog. This is useful for users who don't feel comfortable, (and rightly so), about leaving a connection open to a server that they probably don't control that could potentially be running malicious code to control their own computer. When this is enabled and configured, the computer running the addon will automatically start it's own server when NVDA (or the addon itself), starts. You will need to poke an NVDA remote-shaped hole (and by NVDA Remote-shaped, I mean TCP Port 6837), in your computer's firewall, as well as the firewall of any nat router (you only need to add a port forward in the router of you want to access this externally). I'll probably be adding the ability to specify a custom port in the options dialog for auto self-hosted servers soon, so if your interested in that, keep an eye on this repository.  
  
That's all this version adds for now. If you have ideas, suggestions, bugs, feel free to email me or file an issue here on git hub.