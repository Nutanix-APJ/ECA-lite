.. Adding labels to the beginning of your lab is helpful for linking to the lab from other pages
.. _example_lab_3:

-------------
Networking
-------------

Creating an Unmanaged Client Network
++++++++++++++++++++++++++++++++++++

In this exercise you will create an unmanaged network.

1.	Log on to your cluster’s Prism UI (Element) as the **admin** user.

2.	Click the **gear** icon, scroll down in **Settings** to the **Network** section and click **Network Configuration**.

3.	Click **Virtual Networks** if not already selected.

   .. figure:: images/1.png
 
4.	Click **Create Network**

5.	Fill out the **Create Network** dialog box as follows:

 * Name: **Unmanaged Client Network**

 * VLAN ID: **<Refer to Cluster Configuration Information>**

 * Enable IP address Management: **Leave unchecked**

    .. figure:: images/3.png

6.	Click **Save** to create the network.

 
Managing Open vSwitch (OVS)
++++++++++++++++++++++++++++++++++++

In this exercise you will explore a few commands to manage Open vSwitch (OVS) from the CVM and use those commands to build an additional virtual switch.

1.	Using PuTTY, establish an SSH connection to one of your CVMs and log on with the **nutanix** user and password **(Refer to Cluster Configuration Guide)**.

2.	Use **allssh** to execute commands on all CVMs. To view network interface information, type the command:

  .. code-block:: bash

     allssh manage_ovs show_interfaces
 
 * How many network interfaces are on each node?
 * How many network interfaces are 10GbE?
 * How many network interfaces are 1GbE?

3.	To list existing bridges for each Nutanix node in the cluster, type the command:

  .. code-block:: bash

     allssh manage_ovs show_bridges

 * How many bridges are on each node?

4.	To show bridge uplinks for each Nutanix node in the cluster, type the command:

  .. code-block:: bash

    allssh manage_ovs show_uplinks

 * Which network interfaces are on bond (or port) br0-up of the f