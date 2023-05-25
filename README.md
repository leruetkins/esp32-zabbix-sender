# ESP32ZabbixSender
Library to realize the zabbix-sender on ESP32-Arduino

# How to install this library to Arduino IDE
## Use git command
(Windows and default arduino setting)

    cd %USERPROFILE%\Documents\Arduino\libraries
    git clone https://github.com/leruetkins/ESP32ZabbixSender.git
## Use ZIP import function of the Arduino IDE
Google it

# Usage
See `sample_ESP32ZabbixSender/sample_ESP32ZabbixSender.ino`

    ESP32ZabbixSender zSender;
    zSender.Init(IPAddress(192, 168, 35, 14), 10051, "IOTBOARD_00"); // Init zabbix server address, port, and hostname of item
    zSender.ClearItem(); // clear item list
    zSender.AddItem("integerKey", 10);
    zSender.AddItem("floatKey", 3.14);
    zSender.AddItem("stringKey", "Hello, Zabbix!");
    if (zSender.Send() == EXIT_FAILURE){ // send packet
        // error handling
    }

# Based on:  
https://github.com/zaphodus/ESP8266ZabbixSender
