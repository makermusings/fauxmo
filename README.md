# fauxmo
**Emulated Belkin WeMo devices that work with the Amazon Echo**

Visit [this Maker Musings article](http://www.makermusings.com/2015/07/13/amazon-echo-and-home-automation/) to learn more about using this code to integrate
the Amazon Echo with your own home automation.

### Summary

The Amazon Echo will allow you to control a limited number of home automation devices 
by voice. If you want to control device types that it doesn't know about, or perform 
more sophisticated actions, the Echo doesn't provide any native options. This code
emulates the Belkin WeMo devices in software, allowing you to have it appear that
any number of them are on your network and to link their on and off actions to
any code you want.

### Instructions

All of the code to make it work is contained in the single file, `fauxmo.py`. It
requires Python 2.7 and standard libraries. The example handler class that
reacts to on and off commands uses the [python-requests](http://docs.python-requests.org/en/latest/)
library, but could be replaced with code that does the same thing in many
different ways.

Copy the fauxmo.py file to your server and edit the FAUXMOS list for the device names
you want and the URLs to invoke for on and off commands for each one. You can execute it
simply as `./fauxmo.py`. If you want debug output, execute `./fauxmo.py -d`. If you
want it to run for an extended period, you could do something like `nohup ./fauxmo.py &`
or take extra steps to make it run at startup, etc.

**Note:** unless you specify port numbers in the creation of your fauxmo objetcs, your
virtual switch devices will use a different port every time you run fauxmo.py, which will
make it hard for the Echo to find them. So you should plan to either leave the script
running for long periods or choose fixed port numbers.

Once fauxmo.py is running, simply tell your Echo to "Find connected devices". You can
also do this from the Echo App web page.

### Related

- http://www.makermusings.com/2015/07/13/amazon-echo-and-home-automation/
- http://www.makermusings.com/2015/07/18/virtual-wemo-code-for-amazon-echo/
- http://hackaday.com/2015/07/16/how-to-make-amazon-echo-control-fake-wemo-devices/
- https://developer.amazon.com/appsandservices/solutions/alexa/alexa-skills-kit
- https://en.wikipedia.org/wiki/Universal_Plug_and_Play
- http://www.makermusings.com/2015/07/19/home-automation-with-amazon-echo-apps-part-1/
