<div align="center">

## \_\_Simple Winsock Tutorial\_\_


</div>

### Description

This tutorial will teach you the basics of winsock (the winsock OCX control). How to connect to computers, how to be a server, sending and getting data. If you like this, Please vote for me ;)
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Matt Carpenter](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/matt-carpenter.md)
**Level**          |Intermediate
**User Rating**    |4.4 (509 globes from 115 users)
**Compatibility**  |VB 6\.0
**Category**       |[Coding Standards](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/coding-standards__1-43.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/matt-carpenter-simple-winsock-tutorial__1-30413/archive/master.zip)





### Source Code

<p><b><font face="Verdana" size="6">.::Simple Winsock Tutorial ::.<br>
</font></b><font face="Verdana" size="1"><i>-From the author of 'Simple Direct3d
Tutorial w/ source' on PSC!</i></font></p>
<hr>
<p><font face="Verdana"><b>This tutorial will teach you how to use the Winsock
control to make chat programs, multiplayer games, email checkers, and anything
else that uses Winsock!<br>
<br>
<br>
<font size="4"><br>
</font><font size="2">Winsock is a communications 'thingy' that lets you
communicate with other computers via network/internet. Using TCP/IP or UDP
protocols, you can send data from one computer to another.  We will be
using the Winsock control with visual basic. First, open up visual basic, then
add the Winsock Control. I also assume that you know what a port is...<br>
<br>
Add one to your form.  Now, make 2 command buttons. Label one 'Connect' and
the other 'Host'. <br>
Under the 'connect' button, add the following code:<br>
<br>
</font></b><font size="2">Host = inputbox("Enter the host's computer name
or ip address:")<br>
Port = inputbox("Enter the host's port to connect to:")<br>
Winsock1.connect host, port<br>
<br>
<b>That code let you specify the host computers name/ip address, and the port to
connect to on it. Now, add the following code to the 'Host' button.<br>
<br>
</b>Port = inputbox("What port do you want to host on?")<br>
Winsock1.localport = Port<br>
Winsock1.Listen<br>
<br>
<b>If you were to click the 'host' button, it would activate the server and wait
for somebody to try to connect.<br>
<br>
Now, double click the Winsock control and go to the sub
'winsock1_ConnectionRequest'. Under that, put this code.<br>
<br>
</b>if winsock1.state <> sckclosed then winsock1.close  <font color="#008000">'Got
to do this to make sure the Winsock control isn't already being used.</font><br>
winsock1.accept RequestID<br>
<br>
<b>That code simply let the client connect. Now, add a 3rd button to the form
and call it 'Send'. Under it, add this code.<br>
<br>
</b>Text = inputbox("Send what text?")<br>
winsock1.senddata text<br>
<br>
<b>When you click that, it sends data to the other computer, no matter if you
are the host or the client. You need a way to receive this data on both, so
double click the Winsock control, then go to the 'winsock1_RecieveData' sub (or
something like that). Put in this code.<br>
<br>
</b></font><font size="2">winsock1.getdata(data,vbstring,bytestotal)<br>
<i>or is it winsock1.getdata data,vbstring,bytestotal? I think I might be mixing c++ syntax w/ visual basic :-/<br></i>
msgbox Data<br>
<br>
<b>This displays the data that the other user sent you. </b> <br>
<br>
<b>I guess I really didn't go in depth with this article, but it is all REALLY
simple. Maybe you want to send player coordinates if you are making a
multiplayer game, or send messages if it's a chat program that you want to make.
Doesn't really matter.<br>
<br>
To test this program, compile it, then open 2 instances of it. in one, click the
'host' button and enter the port 100 (Just because. You could do any port you
want (1 to 1000 or higher!))<br>
In the other one, click 'Connect' Then type in 'Localhost' for the server, and
the port should be, guess what, 100! <br>
This will create a loop, and you will connect to your self. On one of the
instances, click send, then type in a message. No, don't just type in any message,
type 'Hello World!'. How original is that? Click OK, then a message box from the
other instance should pop up with the same message. You could also use 127.0.0.1
for the host instead of Localhost, because that is the same thing as Localhost,
only in an IP address.  <br>
I guess this doesn't TEACH you how to make multiplayer games, but at least you
know how to now...<br>
<br>
That was a real simple tutorial. Not much else to say, except, Please vote for
me if you liked this!</b></font></font></p>

