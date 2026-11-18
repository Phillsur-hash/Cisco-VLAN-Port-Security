Cisco Switch Port Security Configuration

Project Overview:
This project demonstrates how to configure Port Security on a Cisco switch using the Cisco IOS Command-Line Interface (CLI).
Port Security is a Layer 2 security feature that helps prevent unauthorized devices from accessing a network through switch ports. In this project, Port Security is enabled on two switch interfaces (FastEthernet 0/1 and FastEthernet 0/2).
Each interface is configured to allow a maximum of one MAC address, automatically learn MAC addresses using sticky learning, and shut down the port if a security violation occurs.
Objectives

    Configure Port Security on Cisco switch interfaces.
    Limit each switch port to one MAC address.
    Enable sticky MAC address learning.
    Configure the violation mode to shut down ports when a security violation occurs.
    Enable Port Security on access ports.
    Verify Port Security settings using Cisco IOS commands.

Network Configuration
Device	Interface	Maximum MAC Addresses	Violation Mode	MAC Address Learning
S1	FastEthernet 0/1	1	Shutdown	Sticky
S1	FastEthernet 0/2	1	Shutdown	Sticky
Configuration Steps
1. Access Global Configuration Mode:
S1> enable
S1# configure terminal

2. Configure Port Security on FastEthernet 0/1:
S1(config)# interface f0/1
S1(config-if)# switchport port-security maximum 1
S1(config-if)# switchport port-security violation shutdown
S1(config-if)# switchport port-security mac-address sticky

3. Configure Port Security on FastEthernet 0/2:
S1(config)# interface f0/2
S1(config-if)# switchport port-security maximum 1
S1(config-if)# switchport port-security violation shutdown
S1(config-if)# switchport port-security mac-address sticky

4. Configure Access Mode and Enable Port Security:
S1(config-if)# switchport mode access
S1(config-if)# switchport port-security

5. Verify Port Security Configuration:
Use the following commands to verify that Port Security is enabled on both interfaces:
FastEthernet 0/1:
S1(config-if)# do show port-security interface f0/1

FastEthernet 0/2:
S1# show port-security interface f0/2

Verification Results

The verification commands confirmed the following settings on both interfaces:
Security Setting	FastEthernet 0/1	FastEthernet 0/2
Port Security	Enabled	Enabled
Port Status	Secure-up	Secure-up
Violation Mode	Shutdown	Shutdown
Maximum MAC Addresses	1	1
Total MAC Addresses	0	0
Configured MAC Addresses	0	0
Sticky MAC Addresses	0	0
Security Violation Count	0	0

Verification Summary
    Port Security is enabled on both interfaces.
    Both interfaces are operating in access mode.
    Each interface is configured to allow a maximum of one MAC address.
    Sticky MAC address learning is configured.
    The violation mode is set to shutdown.
    Both interfaces show a Secure-up status.
    No security violations have been recorded.

Note: The output shows zero learned MAC addresses on both interfaces. Sticky MAC learning is configured, but a device must generate traffic through the interface before its MAC address is dynamically learned and added to the running configuration.
Technologies Used

    Cisco IOS
    Cisco Catalyst Switch
    Switch Port Security
    MAC Address Filtering
    Sticky MAC Address Learning
    Cisco Command-Line Interface (CLI)
    Networking Fundamentals

Key Concepts Learned

    Port Security: A Cisco switch feature that restricts which devices can connect through a switch port.
    Maximum MAC Addresses: Limits the number of MAC addresses permitted on a switch interface.
    Sticky MAC Address Learning: Automatically learns MAC addresses and adds them to the running configuration.
    Violation Mode: Determines what happens when an unauthorized MAC address attempts to access a secured port.
    Shutdown Mode: Places the port into an error-disabled state when a security violation occurs.
    Access Mode: Configures a switch interface to operate as an access port assigned to a single VLAN.

Conclusion

This project demonstrates how to configure and enable Port Security on a Cisco switch to help protect a network against unauthorized device connections.
By limiting each interface to one MAC address, enabling sticky MAC address learning, and configuring the violation mode to shutdown, 
switch administrators can add an additional layer of security to their network infrastructure.
The successful verification of both interfaces confirms that Port Security is enabled and operating as configured.
This project reinforces fundamental Cisco switching and network security skills used in enterprise networking environments.

Project: Cisco Switch Port Security Configuration

Category: Networking / Cisco Switching / Network Security

Author: Phillip Surrett
