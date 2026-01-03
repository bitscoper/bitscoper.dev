---
date: "2023-04-02T21:51:14+00:00"
title: "How to Use sysfs to Restart Failed PCI Devices in Fedora"
---

If you’re working with PCI (Peripheral Component Interconnect) devices in _Fedora_, you may occasionally run into situations where a device fails or becomes unresponsive. In these cases, the _sysfs_ filesystem provides a powerful set of tools for managing your devices.

### a) Identify the Failed Device

List all of the PCI devices on your lovely system and their current status.  
`sudo lspci -v`  
Look for any devices that have a status of “failed” or “unclaimed.” Make a note of the device’s address, which will be listed in the format “XX:XX.X” where X is a hexadecimal digit.

### b) Locate the Device in _sysfs_

Once you have identified the address of the failed device, you can locate it in the _sysfs_ filesystem. The _sysfs_ filesystem is mounted at **/sys**, so navigate to the device’s directory.  
`cd /sys/bus/pci/devices/XX:XX.X/`  
Replace “XX:XX.X” with the address of the failed device that you noted in step 1.

### c) Check the Device Status

Before attempting to restart the device, it’s a good practice to check its current status. Read the contents of the **status** file in the device’s directory.  
`sudo cat status`  
If the file contains the string “error,” “failed,” or “unrecoverable,” then the device has encountered a serious error and may not be recoverable.

### d) Reset the Device

If the device is not in an unrecoverable state, you can attempt to reset it by writing **1** to the **reset** file in the device’s directory.  
`echo 1 | sudo tee reset`  
This will send a reset command to the device and attempt to bring it back online.

### e) Check the Device Status Again

After resetting the device, you should check its status again to see if the reset was successful. Display the contents of the **status** file.  
`sudo cat status`  
If the file contains the string “okay,” then the device has been successfully reset and should be functioning normally.

### f) Re-Enable the Device

In some cases, a failed device may be disabled by the system after encountering an error. If the device is disabled, you will need to re-enable it before it can be used again. You can do this by writing **1** to the **enable** file in the device’s directory.  
`echo 1 | sudo tee enable`

### g) Test the Device

Once you have reset and re-enabled the device, you should test it to ensure that it is functioning properly. This may involve running diagnostic software, testing its functionality within an application, or simply checking its status again using the commands in steps 3 and 5.

---

### Documentation

<https://man7.org/linux/man-pages/man5/sysfs.5.html>
