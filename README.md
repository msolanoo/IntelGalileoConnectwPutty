IntelGalileoConnectwPutty
=========================

Best Known Working method to connect to Intel Galileo with putty using standard ethernet cable

You can connect to the Linux OS in the Galileo in several ways. I realized Ethernet is one of the simplest.

Preparation:
- Ethernet cable
- Arduino IDE

Procedure:
- Start Arduino IDE and connect to your Galileo with the USB cable
- Send the following sketch to your Galileo:

void setup() {
  // put your setup code here, to run once:
system("telnetd -l /bin/sh");
system("ifconfig eth0 169.254.1.1 netmask 255.255.0.0 up");
}


void loop() {
  // put your main code here, to run repeatedly: 
  
}

- Connect the Ethernet cable between your computer and your Galileo
- Start putty and set it up to access the IP address 169.254.1.1 in Port 22.  User Name: root

Congrats! You should be able to connect to your Galileo!!!

If you wish to connect to your Galileo using your home router instead of connecting it directly to your computer, use the following sketch:

In Setup: system("telnetd -l /bin/sh");
In Loop: "ifconfig eth0 > /dev/ttyGS0");

