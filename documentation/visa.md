# Setting up VISA on (k)Ubuntu

National Instruments don't like Ubuntu. While there are packages for other Linux distros (e.g. CentOS), there are none for our friend Ubuntu. To connect to devices over USB/GPIB from an Ubuntu system, you will have to go through the following steps. 

1. Install pyvisa-py: 
    `$ pip3 install pyvisa-py`

2. Install pyusb (to allow for control over USB): 
    `$ pip3 install pyusb`

3. Check the output of python3 -m visa info and see if it is as follows. If not, you're already going wrong. (Check online for help!)

   ```
   Machine Details:
      Platform ID:    Linux-5.3.0-26-generic-x86_64-with-debian-buster-sid
      Processor:      x86_64

   Python:
      Implementation: CPython
      Executable:     /home/joseph/anaconda3/bin/python3
      Version:        3.7.6
      Compiler:       GCC 7.3.0
      Bits:           64bit
      Build:          Jan  8 2020 19:59:22 (#default)
      Unicode:        UCS4

   PyVISA Version: 1.10.1

   Backends:
      ni:
         Version: 1.10.1 (bundled with PyVISA)
         Binary library: Not found
      py:
         Version: 0.3.1
         ASRL INSTR:
            Please install PySerial (>=3.0) to use this resource type.
            No module named 'serial'
         USB INSTR: Available via PyUSB (1.0.2). Backend: libusb1
         USB RAW: Available via PyUSB (1.0.2). Backend: libusb1
         TCPIP INSTR: Available 
         TCPIP SOCKET: Available 
         GPIB INSTR:
            Please install linux-gpib to use this resource type.
            No module named 'gpib'
    ```    

4. Follow the steps from [this stackexchange answer](https://stackoverflow.com/questions/52256123/unable-to-get-full-visa-address-that-includes-the-serial-number) . 

   1. `$ sudo groupadd usbusers`

   2. `$ sudo usermod -a -G usbusers <USERNAME>`

   3. Reboot

   4. `$ sudo cp  /etc/udev/rules.d/99-com.rules  /etc/udev/rules.d/99-com.rules.BAK` (to backup file if it exists)

   5. `$ sudo nano  /etc/udev/rules.d/99-com.rules`

   6. Add the following:  `SUBSYSTEM=="usb", MODE="0666", GROUP="usbusers"`

   7. `$ /etc/init.d/udev  restart`

5. You might need to run `$ sudo rmmod usbtmc`. When the instrument is plugged in, the usbtmc driver grabs it (from my understanding). You have to remove this driver from the instrument before it can be seen by pyvisa.
