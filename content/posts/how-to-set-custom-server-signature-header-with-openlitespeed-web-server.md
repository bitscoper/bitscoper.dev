---
date: "2022-09-28T20:52:00+00:00"
title: "How to Set Custom Server Signature Header With OpenLiteSpeed Web Server"
---

Go to your _OpenLiteSpeed Web Server_‘s _WebAdmin Console_ and log in.

### a) Disabling Default Server Signature

Navigate to **_Server Configuration_ > _General Settings_** and then click on its related **_Edit_** icon. Set the **_Server Signature_** option to **_Hide Full Header_** from its dropdown selection list. Then click on **_Save_** icon.

### b) Setting Custom Header

Custom headers can only be set for **context** levels.  
Now, navigate to **_Virtual Hosts_** and then click on **_View_** icon related to your desired virtual host. Create a context for the virtual host by navigating to **_Context_ > _Context List_** and then clicking on **_Add_** icon. Then, under **_New Context_**, set **_Type_** option to **_Static_** from its dropdown selection list and then click on **_Next_** icon. After that, under **_Static Context Definition_**, you need to configure the following options:

- We are about to set the custom header for **Document Root** (**_$DOC_ROOT_**) and that’s why we have to set **_URI_** option to **_/_**.
- And **_Accessible_** option must be set to **_Yes_**. (Otherwise, **Error 403** will be experienced throughout the **Document Root**.)
- In **_Header Operations_** field, put your lovely custom server signature header.  
  `Server: "TeleChirkut"`  
  Finally, click on **_Save_** icon.

### c) Restarting

Changes will take effect after you give the _OpenLiteSpeed Web Server_ a graceful restart. (Graceful restart ensures zero downtime.)

- **In case of its _WebAdmin Console_:** Just click on **_Graceful Restart_** icon and then proceed to **_Yes_**.
- **In case of _systemd_:** `sudo systemctl restart openlitespeed.service` or `sudo systemctl restart lsws.service`

---

### Documentations

- <https://openlitespeed.org/kb/how-to-set-up-custom-headers/>
- <https://openlitespeed.org/kb/command-references-for-administration/>
