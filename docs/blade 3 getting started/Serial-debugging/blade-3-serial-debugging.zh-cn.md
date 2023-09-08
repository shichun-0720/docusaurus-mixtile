---
title: Use serial debugging
type: docs
weight: 20
---

Developers can get the serial debugging information of Mixtile Blade 3 by connecting it to a PC via its DEBUG serial port.

# Serial debugging on Windows

Please follow the instructions below to complete serial debugging on Windows.

   1. Prepare tools.
   
      You need to prepare the following tools:
   
      - a USB to TTL converter (for example: FT232)
   
      - a Windows PC
   
      - a serial debugging tool (for example: SecureCRT)

   2. Connect hardware.
   
      1. Connect the USB to TTL converter to your Mixtile Blade 3.
         
         Mixtile Blade 3's DEBUG serial port has three pins: GND, TXD and RXD. The USB to TTL converter you're using may have more pins.
         
         You have to connect the three pins of Mixtile Blade 3 to the corresponding pins of your USB to TTL converter.
   
      2. Connect the USB to TTL converter to your PC.

   3. Download and install a driver.
   
      1. Download a driver according to the USB to TTL converter that you're using.
   
      2. Unzip the zip file and select the corresponding file (.exe) to install according the PC architecture (whether it's 32-bit or 64-bit).
         
         If only one installation file (.exe) is available, select it to install.

   4. Check your Mixtile Blade 3's serial port via your PC's Device Manager.
   
      <img width="797" alt="Windows Device Manager - Serial port" src="https://user-images.githubusercontent.com/116132562/198246660-7ca2396b-2fa4-4d9c-aeff-e1128df796cd.png">

   5. Install a serial debugging tool.
   
      SecureCRT is one of serial debugging tool generally used on Windows, and is used for illustration here.
   
      Select the corresponding file (.exe or .msi) to install according to the PC architecture (whether it's 32-bit or 64-bit).

   6. Configure the serial debugging tool.
   
      1. Open SecureCRT.
         
         The first time you use SecureCRT, it will jump out of the Quick Connect configuration directory.
   
      2. Complete the settings as shown below:
         
         <img width="796" alt="Setting serial port parameters on Windows" src="https://user-images.githubusercontent.com/116132562/198246943-fbd8a35a-d85c-47c9-8313-1cddc7c02c28.png">
   
      3. Click Connect.
         
         You'll see the following output.
         
         <img width="802" alt="SecureCRT output on Windows" src="https://user-images.githubusercontent.com/116132562/198247064-fd2cbcbf-6a09-436b-8fa4-adf2b4ace95b.png">

# Serial debugging on Ubuntu

Please follow the instructions below to complete serial debugging on Ubuntu.

   1. Prepare tools.
   
      You need to prepare the following tools:
   
      - a USB to TTL converter (for example: F232)
   
      - a Ubuntu PC
   
      - a serial debugging tool (for example: picocom)

   2. Connect hardware.
   
      1. Connect the USB to TTL converter to your Mixtile Blade 3.
         
         Mixtile Blade 3's DEBUG serial port has three pins: GND, TXD and RXD. The USB to TTL converter you're using may have more pins.
         
         You have to connect the three pins of Mixtile Blade 3 to the corresponding pins of your USB to TTL converter.
   
      2. Connect the USB to TTL converter to your PC.

   3. Install a serial debugging tool.
   
      Picocom is one of serial debugging tool generally used on Ubuntu, and is used for illustration here.
   
      ```
      sudo apt-get update
      sudo apt-get install picocom
      ```

   4. View serial device number.
   
      After the USB to TTL converter is connected to the PC, the device number of the serial is displayed in the `/dev directory as ttyUSB[0, 1, 2....]`. Take ttyUSB0 as an example:
   
      ```
      username@ubuntu:~$ ls /dev/ttyUSB0
      /dev/ttyUSB0
      ```

   5. Operate the serial debugging tool.
   
      `-b` is to set the baud rate.
   
      ```
      sudo picocom -b 1500000 /dev/ttyUSB0
      picocom v2.2
   
      port is        : /dev/ttyUSB0
      flowcontrol    : none
      baudrate is    : 1500000
      parity is      : none
      databits are   : 8
      stopbits are   : 1
      escape is      : C-a
      noinit is      : no
      noreset is     : no
      nolock is      : no
      send_cmd is    : sz -vv
      receive_cmd is : rz -vv -E
      imap is        :
      omap is        :
      emap is        : crcrlf,delbs,
   
      Type [C-a] [C-h] to see avaiable commands
   
      Terminal ready
      console:/ $
      console:/ $
      console:/ $
      console:/ $
      ```

   6. Exit picocom.
   
      1. Press the key combination CTRL+A.
   
      2. Keep pressing CTRL but release A.
   
      3. Keep pressing CTRL and press Q.

# Serial debugging on macOS

Please follow the instructions below to complete serial debugging on macOS.

   1. Prepare tools.
   
      You need to prepare the following tools:
   
      - a USB to TTL converter (for example: FT232)
   
      - a macOS PC
   
      - a serial debugging tool (for example: picocom)

   2. Connect hardware.
   
      1. Connect the USB to TTL converter to your Mixtile Blade 3.
         
         Mixtile Blade 3's DEBUG serial port has three pins: GND, TXD and RXD. The USB to TTL converter you're using may have more pins.
         
         You have to connect the three pins of Mixtile Blade 3 to the corresponding pins of your USB to TTL converter.
   
      2. Connect the USB to TTL converter to your PC.

   3. Install a serial debugging tool.
   
      Picocom is one of serial debugging tool generally used on macOS, and is used for illustration here.
   
      ```
      $ brew install picocom
      ```
   
      **Note**: You need to install the brew tool before using the above command. You can use the following demand to install brew.
   
      ```
      /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
      ```

   4. View serial device number.
   
      After the USB to TTL converter is connected to the PC, the device number of the serial is displayed in the `/dev directory as ttyUSB[0, 1, 2....]`. Take ttyUSB0 as an example:
   
      ```
      username@ubuntu:~$ ls /dev/ttyUSB0
      /dev/ttyUSB0
      ```

   5. Operate the serial debugging tool.
   
      `-b` is to set the baud rate.
   
      ```
      sudo picocom -b 1500000 /dev/ttyUSB0
      picocom v2.2

      port is        : /dev/ttyUSB0
      flowcontrol    : none
      baudrate is    : 1500000
      parity is      : none
      databits are   : 8
      stopbits are   : 1
      escape is      : C-a
      noinit is      : no
      noreset is     : no
      nolock is      : no
      send_cmd is    : sz -vv
      receive_cmd is : rz -vv -E
      imap is        :
      omap is        :
      emap is        : crcrlf,delbs,

      Type [C-a] [C-h] to see avaiable commands

      Terminal ready
      console:/ $
      console:/ $
      console:/ $
      console:/ $
      ```

   6. Exit picocom.
   
      1. Press the key combination CTRL+A.
   
      2. Keep pressing CTRL but release A.
   
      3. Keep pressing CTRL and press Q.
