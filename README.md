# VictronVEDirectArduino
Light-weight Arduino library to read basic data using the VE.Direct protocol from Victron Energy

Built as part of a larger project, now making it available separately in case others find it useful.

Setup:
 - An Arduino(ish) board 
 - A Victron Energy device that sends serial data using the text version of the VE.Direct protocol
 - A 5v to 3.3v serial converter (BMV is 3.3v - don't plug it directly into an Arduino!)
 - Plugged into the Arduino on a serial port (eg Serial1, Serial2 etc)
 - See also: https://www.victronenergy.com/live/vedirect_protocol:faq
 - Developed and tested with a BMV-700 battery monitor
 - Distributed under an MIT license - see LICENCE.txt
 - Developed and not tested with a MPPT 100/30

Provides:
 - Access to basic energy readings - Volts, Power, Current, State of Charge (SOC)
 - A diagnostic "full dump" of everything coming from the device  

### Usage:
    #include "VEDirect.h"
    
    VEDirect my_bmv(Serial3);
    
    if my_bmv.begin() {
        my_int32 = my_bmv.read(VE_SOC);
    }
    
    // VE_SOC, VE_VOLTAGE, VE_CURRENT, VE_POWER

