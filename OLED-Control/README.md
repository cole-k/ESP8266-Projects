#OLED-Control

This is a simple script to make the ESP8266 do the following:

* Connect to a WiFi network.
* Host a local server on that WiFi network. The IP for this is output via serial and on the display itself.
* Change the OLED display to reflect whatever input you give it

<a href=https://drive.google.com/file/d/0B7b5Gf6me7nWZjFZeVAzS0tMVTA/view>Here is a video</a> that showcases both the program in action and my inability to focus the camera. Note that it is of an earlier variant that did not display the IP of its server when it started up.

###Some things to consider

1. You need to change line 65 to the name of your WiFi network ("WIFINAME") and its password ("WIFIPASSWORD")
2. By default, this expects digital pin 5 to go to the SDA of the OLED and digital pin 6 to go to the SCL (you can change this on line 3 at i2c.setup)
3. Because it uses GET and not POST, only alphanumerics are officially supported as inputs. 
4. Newlines do translate to different lines on the OLED display, but as of right now not more than 1 (see the previous point).
5. Sending SHUTDOWN as an input will stop the program, sort of (as of right now it mostly just restarts it)

###For the future

* I intend on doing general housekeeping on the code (cleaning it up, adding more comments, flexibility, etc.)
* I intend on switching from GET to POST
* I intend on making the text displayed a variable or stored somehow so that when another user connects they see what text is currently being displayed (perhaps even update it in real time for all connected users)
* I intend on looking into potentially using Arduino instead of Lua (it is unlikely that I will do this, but I intend on looking into it)

###Some credits

There are credits to third-party examples or tutorials that I found helpful in writing my own code

* [Ashishware](http://ashishware.com/Esp8266Display.shtml#) for a very concise and readable example of the u8g library for i2c control
* [Random nerd tutorials](http://randomnerdtutorials.com/esp8266-web-server/) for a good example of server hosting
