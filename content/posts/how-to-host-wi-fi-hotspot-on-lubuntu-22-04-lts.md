---
date: "2022-08-25T20:47:00+00:00"
title: "How to Host Wi-Fi Hotspot on Lubuntu 22.04 LTS"
---

### a) Configuring Hotspot

Navigate to **_Application Menu > Preferences > Advanced Network Configuration_** or right click on desktop panel’s network icon and go to **_Edit Connections_**. Click on **_Add a new connection_** icon (**_+_**) and the next dialog box will ask you for your desired connection type. Select **_Wi-Fi_** option under **_Hardware_** group and then proceed with **_Create_** button. Set the **_Connection name_** to something, by which you will recognize the connection inside your lovely system.

Under **_General_** tab:

- Check **_Connect automatically with priority_** and set it to **1**. (Assuming, we set this option, of the connection from which we will share to the hotspot, to 0.)
- Check **_All users may connect to this network_**.
- Select **_Metered Connection_** to **_Automatic_** option.

Under **_Wi-Fi_** tab:

- Set a **_SSID_** (Service Set Identifier) by which other devices will find this hotspot.
- Set **_Mode_** to **_Hotspot_** option.
- Set **_Band_** to **_Automatic_** option.
- Assign **_Device_** to the Wi-Fi card we want to be the hotspot. Its name may start with **wlan** or **wlp** (such as **wlan0** or **wlp2s0b1**).

Under **_Wi-Fi Security_** tab:

- Select **_Security_** to **_WPA & WPA2 Personal_** or **_WPA3 Personal_**.
- Set the password.

Under both **IPv4 Settings** and **IPv6 Settings**:

- Select **_Method_** to **_Shared to other computers_** option.

### b) Activating Hotspot

Click on the desktop panel’s network icon and then click on the connection name of the hotspot. A notification should appear mentioning the successful connection.
