# Pir-Sensor
Turns monitor on and off

Download files to your root directory on your pi

Go here to install wiring pi [if you already haven't!] follow the directions there!  

http://wiringpi.com/download-and-install/
___________________________________________________________________________________

NOW for your sensor... Please hook up all wiring to your GPIO 
Hook up your power and ground wire to the appropriate GPIO pins [Power pin 2, Ground pin 6]
Hook up your trigger wire to GPIO Pin 11 which is called GPIO17

chmod all files:
From a terminal window in your root directory:

sudo chmod +x pir.py

sudo chmod +x monitor_off.sh

sudo chmod +x monitor_on.sh

Editing pir.py

Go to this line:
   PIR_PIN = 17        # Pin 11 on the board
   
   IF you want to change PIR_PIN for some reason:
   
   You will need to change this to the pin you're using on the pi for your sensor, to make it easy I would just use it the way it's setup.
   Remember that what the pi reads and what the actual pin number is is not the same.
   
   Google RPI3 GPIO pins and you'll get plenty of pictures of it.
   
   ___________________________________________________________________________________
   
   Last step:
   
   In a terminal window from your root directory enter:
   
   sudo crontab -e
   
   On the last line enter:
   
   @reboot python /home/pi/pir.py &
   
   Hit CRTL-O to save
   then exit
   
   Reboot your pi
   
   _______________________________________________________________
   
   OTHER ADJUSTMENTS:
   
   In the pir.py go to the line:
   
   SHUTOFF_DELAY = 20  # seconds
   
   That's how long if NO motion is dectected the pi will shut off the screen.  Change it to your desired number of seconds.

   Other things:
   If you don't want to put this in  your home directory then you can clone to the directory of your choice BUT remember to adjust your path in crontab... or it won't work!
