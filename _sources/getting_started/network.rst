=============
Network Setup
=============

.. note::

    Wired connection is preferred.

.. contents::
    :local:

Remote PC Network Setup
=======================

.. note::

    Wired connection is preferred.

1.  Connect to the robot's network via a wired connection or its wireless access point.

    *   If connecting to wireless access point, the SSID will be something like ``Unitree_GoXXXXXXX`` and its password is ``00000000`` (eight zeros).

2.  Get your computer's network interface using the ``ifconfig`` command.
    You will see output similar to that below.

    .. code-block:: console

        $ ifconfig
        enp2s0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
                inet 192.168.0.193  netmask 255.255.255.0  broadcast 192.168.0.255

        wlp0s20f3: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
                inet 192.168.0.183  netmask 255.255.255.0  broadcast 192.168.0.255

    *   Wired network connection interfaces start with ``en``.
        In this case, it is ``enp2s0``.

3.  Set the static IP address of your wired network connection to ``192.168.123.162`` using the following commands.
    Make sure to substitute ``enp2s0`` for the name of your wired network connection interfaces.

    .. code-block:: console

        $ sudo ifconfig enp2s0 down # enp2s0 is YOUR PC Ethernet port
        $ sudo ifconfig enp2s0 192.168.123.162/24
        $ sudo ifconfig enp2s0 up

4.  Ping the Go1's Raspberry Pi computer to test network connectivity.
    If you get results like the one below, you are properly connected.

    .. code-block:: console

        $ ping -c 3 192.168.123.161
        PING 192.168.123.161 (192.168.123.161) 56(84) bytes of data.
        64 bytes from 192.168.123.161: icmp_seq=1 ttl=64 time=0.056 ms
        64 bytes from 192.168.123.161: icmp_seq=2 ttl=64 time=0.054 ms
        64 bytes from 192.168.123.161: icmp_seq=3 ttl=64 time=0.054 ms

        --- 192.168.123.161 ping statistics ---
        3 packets transmitted, 3 received, 0% packet loss, time 2030ms
        rtt min/avg/max/mdev = 0.054/0.054/0.056/0.000 ms

SSH
===

Wireless Connection
-------------------

.. note::

    Wired connection is preferred.

To SSH into the robot on a wired connection:

.. code-block:: console

    $ ssh pi@192.168.12.1
    # password: 123

Once SSH'ed into the RPi, can access other onboard computers via the internal network switch.
For example, to SSH into the Head Nano:

.. code-block:: console

    $ ssh unitree@192.168.123.13
    # password: 123

All Nanos share the same username of ``unitree`` and password of ``123``.
See the :ref:`Go1 EDU Architecture diagram <label-go1-edu-architecture>` for a full list of IP addresses.

Wired Connection
----------------

The network port on the back of the Go1 EDU connects directly to its internal switch.
Because of that, any onboard controller can be directly SSH'ed into.
For example, to SSH into the Bottom Nano:

.. code-block:: console

    $ ssh unitree@192.168.123.15
    # password: 123

All Nanos share the same username of ``unitree`` and password of ``123``.
See the :ref:`Go1 EDU Architecture diagram <label-go1-edu-architecture>` for a full list of IP addresses.

Remote Development
==================

VSCode Remote Development
-------------------------

1.  At Trossen Robotics, we use Microsoft's VSCode and its Remote - SSH extension (also developed
    by Microsoft) for simple remote development.

    a.  `Install VSCode`_ for Ubuntu.

    b.  Open VSCode, Press :kbd:`Ctrl` + :kbd:`P` to launch the Quick Open Menu, and run the following command.

    .. code::

        ext install ms-vscode-remote.remote-ssh

.. _`Install VSCode`: https://code.visualstudio.com/download

2.  In VSCode, press **F1** and run the ``Remote-SSH: Open SSH Host...`` command and select the ``Add New SSH Host`` option.
    Enter the same ``username@ip`` combination you used when opening the SSH connection between your remote computer and the Go1 like ``ssh pi@192.168.12.1`` or ``ssh unitree@192.168.123.15``.
    If prompted, enter the password ``123``.

3.  Once connected, use **File > Open Folder**, and select the directory you wish to operate in, i.e. your ROS workspace if using the ROS Interface.

4.  Your instance of VSCode is now attached to the Go1's Raspberry Pi computer and is open to your development workspace.

5.  You can open terminals in VSCode by pressing :kbd:`Ctrl` + :kbd:`Shift` + :kbd:`\`` or by using
    **Terminal > New Terminal**.
