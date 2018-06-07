#Command Line Commands

This is a list of the standard command line / commands that are included with BeipMU.  Scripts and plug-ins can extend and even replace the built in commands.

To see a short summary of the commands, simply type /help in the BeipMU input window.

The symbols after the command name are the type of parameters.  $ is a string, which is just a single word with no spaces, or multiple words with spaces surrounded with quotes (Ex: "This is a test").  # is a number in decimal.  Parameters in ( ) are optional.  See below for a detailed description of each command. 

##/@
Usage:

    /@ $

Runs a script immediately

Examples:

    /@window.output.writeHTML("<icon exclamation>This is <b>bold!</b>");

##/char
Usage:

    /char <character shortcut>

Examples:

    /char Alpha
    /char Beip

When you are connected to a server from the world list but did not connect a character yet, this will send the character's connect string and BeipMU will show you as connected to that character.  At this point it will be as though you connected through that character initially, as all of that characters triggers/macros/etc will apply. 
This is a separate command because it was frequently the case where someone would /connect to a world, do a WHO to see if their friends were there, and if they were, then do a /char to connect and say hi.  Rather than connecting as their char and disconnecting afterwards.  

##/unchar
Usage:

    /unchar

Examples:

    /char Alpha
    /unchar

Useful when you are connected to a character but you'd like BeipMU to think you're not connected to a character.  For example if your password was wrong, or if the server lets you switch characters without reconnecting.  As BeipMU has no way of knowing what character you really are, this gives you more manual control. 

##/chars
Usage:

    /chars

When connected to a server from the world list, this will list all of the characters in that server that you can use the /chars command on.

##/clear 
Usage:

    /clear 

Clears the output window. 

##/close 
Usage:

    /close 

Closes the current window 

##/connect
Usage:

    /connect <hostname> <port>
    /connect <server shortcut>

Examples:

    /connect fluffmuck.org:8888
    /connect 12.23.34.45:8890
    /connect fluff

This connects to the given server, in the form of hostname and port, or server shortcut.  The shortcut name is the name shown in the tree view of the edit worlds/connect dialog.  Hostnames can be a standard DNS name or just an IP address. 

##/disconnect 
Usage:

    /disconnect 

Disconnects from the current server. 

##/echo 
Usage:

    /echo <on/off> 

Examples:

    /echo on
    /echo off 

Turns the local echo to the output window on/off.  This feature is far less useful due to the history window, but is still available if you do not use the history window or prefer the inline echo in the output window. 

##/gag 
Usage:

    /gag <string> 

Examples:

    /gag "Enemy"
    /gag "it is now nighttime" 

Adds a global trigger whose match string is the gag text and it's action is to gag that line of text.  If a trigger already exists with this string, gag is enabled on it if it wasn't already set to gag.  Added as a quick and simple way to gag something easily, for more power see the trigger dialog. 

##/help 
Usage:

    /help 

Displays the built in help list showing the commands and a simple description of each (see the top of this page for the same list) 

##/idle 
Usage:

    /idle <# idle time in minutes> <text to send> 

Examples:

    /idle 15 "w me=Idling"
    /idle 60 '"I am idling!' 

Sets an idle timer that after the specified amount of idle time will send the given text to the server you're currently connected to.  The minimum idle time is 1 minute, a value of 0 is still 1 minute.  Idle timers and messages are not saved, and only apply to the current window you are in. 

##/log 
Usage:

    /log <filename> 

Example:

    /log "world1.txt" 

Starts logging to the given text file.  Creates a new file if it does not exist and appends to a file if it already exists. 

##/logall 
Usage:

    /logall <filename> 

Identical to the /log command except that it also logs all of the existing text in the output window.  Useful if you forget to start logging when you first connect and don't want to miss what was already said. 

##/new 
Usage:

    /new 

Opens a new window. 

##/puppet 
Usage:

    /puppet <puppet name> 

Examples:

    /puppet zombo
    /puppet dog 

Opens a new window and connects it to the given puppet from the currently connected character in the window you type this command in. 

##/puppets 
Usage:

    /puppets 

Shows a list of all of the available puppets for the current character. 

##/quit
Same as /close

##/rawnetwork
Usage:

    /rawnetwork

Opens up a window to show raw network traffic for the current window. Useful to figure out what's going on with prompts/telnet codes/etc!

##/recall 
Usage:

    /recall <number of lines to go back> <string to search for> 

Examples:

    /recall 50 "Frank"
    /recall 100 Joe* 

Searches the output buffer for the given string and displays it in a list in the output window.  Wildcards are allowed, but only at the beginning or end of the search string.  For example, Joe* would indicate that the line starts with "Joe", *Joe would mean the line ends with "Joe".  No stars just means the line contains the given string. 

##/resetscript 
Usage:

    /resetscript 

Will reset the current scripting engine, removing all currently running scripts and hooks.  This will also switch the scripting language to what is currently set in the preferences dialog, so the language can change after this. 

##/slist 
Usage:

    /slist 

Lists all of the server shortcuts, showing the shortcut, host name, and port as a list in the output window 

##/ttype
Usage:

    /ttype $

Set telnet terminal type (Default = "Beip"). With this you can pretend to be any other terminal type.

##/wall
Usage:

    /wall $

Sends the given string to every connection.