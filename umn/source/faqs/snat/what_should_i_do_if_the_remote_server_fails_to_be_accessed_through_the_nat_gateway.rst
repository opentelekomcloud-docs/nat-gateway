:original_name: nat_faq_0017.html

.. _nat_faq_0017:

What Should I Do If the Remote Server Fails to Be Accessed Through the NAT Gateway?
===================================================================================

If your TCP connection fails when your ECS is accessing a server on the public network through an SNAT rule, perform the following steps:

#. Run the following command to check whether **tcp_tw_recycle** is enabled on the remote server:

   **sysctl -a|grep tcp_tw_recycle**

   If the value of **tcp_tw_recycle** is **1**, **tcp_tw_recycle** is enabled.

#. Run the following command to check the number of lost packets of the remote server:

   **cat /proc/net/netstat \| awk '/TcpExt/ { print $21,$22 }'**

   If the value of **ListenDrops** is not **0**, packet loss occurs, that is, the network is faulty.

Troubleshooting
---------------

**Method 1: Modifying the kernel parameter of the remote server**

-  Run the following command to temporarily modify the parameters (the modification becomes invalid after the server is restarted):

   **sysctl -w net.ipv4.tcp_tw_recycle=0**

-  Perform the following operations to permanently modify the parameters:

   #. Modify the **/etc/sysctl.conf** file:

      **vi /etc/sysctl.conf**

      Add the following content to the file:

      net.ipv4.tcp_tw_recycle=0

   #. Press **Esc**, enter **:wq!**, and save the file and exit.

   #. Run the following command to make the modification take effect:

      **sysctl -p**

**Method 2: Modifying the kernel parameter of the local client**

-  To temporarily modify parameters (the settings become invalid after the local client is restarted), configure the parameter as follows:

   **sysctl -w net.ipv4.tcp_timestamps=0**

-  Perform the following operations to permanently modify the parameters:

   #. Modify the **/etc/sysctl.conf** file:

      **vi /etc/sysctl.conf**

      Add the following content to the file:

      net.ipv4.tcp_timestamps=0

   #. Press **Esc**, enter **:wq!**, and save the file and exit.

   #. Run the following command to make the modification take effect:

      **sysctl -p**
