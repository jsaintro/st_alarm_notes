# HW Setup
1. Attach the smartthings sheild to the arduino
   Note: Match up the pin labels between the two boards.
1. Setup the alternate serial pins
   jumper pin 2 -> 14 (tx3)
   jumper pin 3 -> 15 (rx3)
   set switch on shield to D2/D3
   Note: This allows you to troubleshoot using the serial monitor
   also this is the only way i've gotten everything to work


# Arduino Setup

1. Download the ST_anything project
   ```
   git clone git@github.com:DanielOgorchock/ST_Anything.git 
   ```
1. Copy the Skectes and Libraries folders from the project in othe Arduino directory

1. Open the Arduino App and load the ST_Anything Sketch
   Arduino/Sketches/ST_Anything_Doors_Windows/ST_Anything_Doors_Windows.ino
1. complile the sketch
   (The check icon)
1. Upload the compiled sketch to the arduino

# Pairing smartthings shield with hub
1. Power on the arduion with sheild attached
1. In the App go into pairing mode looking for a device
1. Hit the "switch" button on the St sheild
1. Should pair as an Arduion ThingSheild

# Setup the Device Handler
1. Login to the smarthings api
  https://graph.api.smartthings.com/login/auth
1. Click on "My Device Handlers"
1. Click on "+ New Device Handler"
1. Select "From Code" Tab
1. Paste code from Groovy/ST_Anything_Doors_Windows.groovy file in the repo
1. Click on "Create"
1. Click on "Save"
1. Click on "Publich" -> "For Me"
1. Click on "My Devices"
1. Select your "Arduino ThingShield"
1. Click on Edit 
1. Change type to "St_Anything"
   Note: It's at the bottom of the list
1. Click on Update button
1. Relogin to app on phone
1. Click on the "Arduino thingShield" thing
   You should now see a bunch of tiles

# Verify that everything is working
1. Open up the arduino serial monitor
   You should see a bunch of "Sending" events.  If not check the jumpers from 2/3 to 14/15

# Setup the multiplexer (Breaks out the sensors under the sheild into sepearate virtual ones)
1. In the API
1. select "MySmartApps
1. Select "+New SmartApp
1. Click on Code tab
1. Paste the Groovy/ST_Anything_Doors_Windows/ST_Anything_doors_Windows_Multiplexer.smartapp.groovy
1. Click on "Create"
1. Click on "Save"
1. Click on "Public" -> "For Me"

# Create the Virtual Devices
## Create the handlers
1. Select "My Device Handlers"
1. Select "+Create New Device Handler"
1. Select "From Code"
1. Paste the Groovy/VirtualDevices/VirtualContactSensor.device.groovy
1. Click on "Create"
1. Click on "Save"
1. Click on "Public" -> "For Me"
1. Repeat for:
  "VirtualMotionSensor.device.groovy"
  "VirtualDoorControl.device.groovy"
## Create a device for each contact switch (You will be using)
Type is 

Continue here www.kindrickcoleman.com/index.php/Tech-Blog/total-noob-guide-to-move-your-old-wired-security-system-to-smartthings.html
# Need to 
Create virtual devices for each 

# Customize for your house
1. Edit the schetch
   change the variables to match your zones
