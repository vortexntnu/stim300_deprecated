# Communicate with STIM300 over terminal

Install minicom: 

    sudo apt-get install minicom

Look for device:

    dmesg | grep tty

Open minicom with setings:

    sudo minicom -s

Setup minicom for stim300:

Serial port setup:

    A - Serial Device: /dev/ttyUSB0
    E - 921600 8N1
    F - Disable hardware flow control

Modem and dialing: (Clear option A...I)

    A - 
    * -
    * -
    * -
    I -

Screen and keyboard:

    P - Add linefeed

Save setup as dfl then Exit minicom, and enter again in hex display mode:

    sudo minicom -H

The stim300 is in normal mode and will reapeatidly send the standard datagram.

Enter service mode: write "SERVICEMODE" and press enter

    SERVICEMODE

Clear the screen:

    Ctrl-A c
    
If the incomming datagram feed stopped it means you enter service mode sucsessfully. While in service mode the stim 300 will comunicate with asci characters. Exit minicom and enter in normal ASCI mode:

    Ctrl-A x
    sudo minicom
   
Write ? and press enter, and the STIM300 should send info about available commands

    ?

This will show a list on available commands including how to go back to normal mode.
