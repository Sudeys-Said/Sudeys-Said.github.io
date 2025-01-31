# About me
### Who am I
- Sudeys Said
- 2008
- I am an aspiring future Civil Engineer!
- I have worked with Html&Css and Java main
- Beginner in both and hope to become well versed in both if possible
- I like to play Football, volleyball and any sport really


# Portfolio

### Midterm - Rev the engine through the press of a single button
- Plan 1: Access the ecu
  - Get a software/hardware that can send input through the obd2 port or a reader
    - Issue: cheap ones only take in inputs, the ones that can control throttle costs upward of 500 dollars, and dealers (liers) said it's not possible 
    - Pros: pretty cool, straight forward
- Plan 2: plug computer into the ecu directly
  - splice the scrap engine wires to make a custom wire that connects the ecu port to the pc
    - Issue: wires were damaged, the port handled more than just throttle position and required trial and error
    - Pros: direct communication, cheaper, more educational/interesting
- plan 3: motor with gears that move the potentiometer inside the accelarator
  - cut up the accelarator and remove the pedal, place a screw with a gear and connect it to the potentiometer, and send the input to the stepomotor to move the gear thus moving the the acclarator. The current is then allowed to continue to the throttle position sensor allowing it to rev.
    - Issues: simplistic, required trouble shooting, gears that cam with the stepomotor were useless and required vex gears,
    - Pros: simplistic, functional, modular and cost effective



### Final project - Dual booting ubuntu and windows and setting up an open source obd2 diagnostic on the tv
- Started of setting up and dual booting the computer.
  - Issues faced: currupted windows, currupted usbs
  - Solutions: wiped and re-installed ubuntu and windows
- installation guide:
   - Right click windows or search disk management
   - Right click the partition that has boot in it, and choose shrink volume option
   - Recomended atleast 15-20 GB, make sure with computer module
   - If secure-boot is on, turn it off
     - To check, enter windows+R, type msinfo32 and press enter,
     - To turn it off, hold shift while restarting, enter troubleshoot -> advanced options -> uefi settings
      - Click restart to enter bios, go to security and turn off secure boot
   - Plug in usb and get into bios
   - Boot the ubuntu
   - Choose whatever custoimizations you want but mainly choose the download alongside windows option during the download process
- Installing pyobd:
  - Issue: horrible to follow, not properly organized, requires previous knowledge, somethings wouldn't dow
  - Solution: make our own guide

 
### Pyobd installation guide on ubuntu:
  - Downloading pre-requisites (some of these may require a virtual environemt to download, so go through all of them, and download the ones that don't work in a virtual environment)
    - Python3 and python3-pip
    - libnsl2 and libnel-dev (library that helps with downloading pyobd files)
    - pyserial (for better communication with python)
    - python3-wxgtk4.0
    - build-essential libxml2-dev libxslt1-dev zlib1g-dev
    - Download all the files availabe from pyobd barracuda github
  - Connect to the pyobd directory and start up a virtual environment:
   - To download and run a virtual environment:
     - sudo apt install python3.12-venv
     - python3 -m venv (username)
     - source (username)/bin/activate (run the virtual environment
   - To connect to directory write : 
    - cd ..
    - cd pyobd  
   - give the account access to usb ports:
    - sudo usermod -a -G dialout $USER
    - sudo usermod -a -G tty $USER
   - (restart or log out after entering code above)
    - to test if the code worked: ls /dev/ttyUSB (to see if you can get access to the ports)
 -  Download requirements: 
  - sudo apt-get install dpkg-dev build-essential libjpeg-dev libtiff-dev libsdl1.2-dev libgstreamer-plugins-base1.0-0 libnotify-dev libglut-dev libglut3.12 libsm-dev libgtk-3-dev libwebkit2gtk-4.1-dev libxtst-dev gettext python3-dev python3-pip
  - pip3 install --upgrade pyinstaller
  - sudo apt install libglib2.0-dev libsmbclient-dev libcups2-dev libgirepository1.0-dev libcurl4-openssl-dev libssl-dev libsystemd-dev librsync-dev
  - python3 -m pip install --upgrade pip setuptools wheel
  - sudo apt install build-essential
  - sudo apt install wxpython-tools numpy python3-tornado python3-pint python3-six (remove the ones that get errors and download them seperately)
  - sudo apt install wxpython-tools python3-tornado python3-pint python3-sixpyth (same with here)
  - python3 -m pip install numpy==1.23.3
  - pip install -U numpy
  - sudo apt install python3-pandas python3-spicy
- Write this code and then restart/log out (i recomend a restart):
  - sudo usermod -a -G dialout $USER
  - sudo usermod -a -G tty $USER
- After restarting, enter:
  - cd pyobd
  - python3 pyobd.py

### How to navigate Pyobd:
  - go to the OBD2 tab
  - configure
  - select /dev/ttyUSB
  - Enter ok, go back to OBD2 tab and connect
