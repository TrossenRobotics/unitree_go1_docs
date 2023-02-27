=============
Network Setup
=============

Remote PC Network Setup
=======================

1.  Connect to the robot's network via a wired connection or its wireless access point.

    *   The wireless access point's SSID will be something like ``Unitree_GoXXXXXXX`` and its password is ``00000000`` (eight zeros).

2.  Configure your connection to be on the ``192.168.123.***`` network segment.
3.  Ping the Raspberry Pi at ``192.168.123.161`` to check connectivity.

    .. code-block:: console

        $ ping -c3 192.168.123.161

SSH
===

Wired Connection
----------------

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

Wireless Connection
-------------------

The network port on the back of the Go1 EDU connects directly to its internal switch.
Because of that, any onboard controller can be directly SSH'ed into.
For example, to SSH into the Bottom Nano:

.. code-block:: console

    $ ssh unitree@192.168.123.15
    # password: 123

All Nanos share the same username of ``unitree`` and password of ``123``.
See the :ref:`Go1 EDU Architecture diagram <label-go1-edu-architecture>` for a full list of IP addresses.
