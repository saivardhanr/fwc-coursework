This code is for utilizing vaman by uploading wifi code into it using the arduino.
Steps to follow:
Intially, Follow all the steps as given in vaman/installation/termuxdebian/termuxubuntu_esp32.txt
Find the circuit diagram i.e vaman_esp32 arduino connections at gadepall/digital-design/main.pdf
Or Download all the files that i provided and do the installations in point3
apt update && apt upgrade
apt install python3-pip
pip3 install platformio
pio lib --global install "stempedia/DabbleESP32"
.pio/build/esp32doit-devkit-v1/firmware.bin
After performing the first step, a setup file will be created. or if you perform step 2 and 3 you can skip the 4th step.
In the setup file, we will get 4 files inside it.
namely: src, .pio, platformio.ini, README.md
Remember to change the main.cpp that is in src folder
#define STASSID "Salient" // Add your network username
#define STAPSK "12345678" // Add your network password
Connect the arduino and vaman together, connect arduino to phone via otg and then vaman to arduino via the installation pdf.
Now we have to be in the setup directory and run pio run .
Remember to remove enable pin EN as soon as it displays Connecting... and then remove 0 pin when it displays writing 100% and before Leaving...
Once after succesfully uploading the code, we can upload new code using pio run -t nobuild -t upload --upload-port 192.168.210.X
