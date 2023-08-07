# Network IP Address Conflict Resolution

This guide outlines the steps to resolve an IP address conflict issue on a network. The process involves identifying conflicting IP addresses, modifying network settings, and confirming resolution.

## Overview

IP address conflicts can disrupt network communication. This guide provides steps to identify and resolve such conflicts efficiently.

## Steps

1. **Identify Conflicting IP Address:**
   - Open the command prompt.
   - Type the following command and press Enter:
     ```cmd
     arp -a
     ```
   - The device's IP address is listed as the interface address at the top of the list (e.g., `<Device1_IP>`).
   - Note down another device's IP address (e.g., `<Device2_IP>`) for reference.

2. **Network Configuration:**
   - Open "Network & Internet Settings."
   - Navigate to "Network and Sharing Center."
   - Click on "Change adapter settings."
   - Right-click the active Ethernet network connection.
     - Choose "Properties."
   - Select "Internet Protocol Version 4 (TCP/IPv4)."
     - Click "Properties."
   - Press the "Tab" key (a subnet mask will be provided).
     - Click "OK."
     - Click "OK."

3. **Identify Computer's IPv4 Address:**
   - Return to the command prompt.
   - Type the following command and press Enter:
     ```cmd
     ipconfig /all
     ```
   - Scroll up to find the Ethernet network connection.
     - Identify the computer's current IPv4 address.
   - Note: A warning about IP address duplication may appear.
   - Observe a preferred IP address (e.g., `<APIPA_Address>`), which is an APIPA address.

4. **Confirm IP Address Conflict:**
   - Type the following command and press Enter:
     ```cmd
     arp -a
     ```
   - Confirm the IP address duplication.
     - The local computer's IPv4 address may appear as an APIPA IP address.
     - An APIPA network address might be listed in the ARP table to support other APIPA devices.

5. **Modify Network Settings:**
   - Open the Network connection interface window.
   - Access Ethernet properties.
   - Open "Internet Protocol Version 4" properties.
   - Select "Obtain an IP address automatically."
     - Click "OK."

6. **Confirm Resolution:**
   - Run the `arp -a` command again.
   - Verify that the unique IP address has been changed and the APIPA address has been removed.

7. **Conclusion:**
   - Close the command prompt and any open windows.

## Conclusion

Resolving IP address conflicts is crucial for maintaining smooth network operations. By following these steps, you can identify, address, and verify the resolution of IP address conflicts effectively.
