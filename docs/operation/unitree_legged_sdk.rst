============================
Using the unitree_legged_sdk
============================

.. note::

    This guide is written with `v3.8.0`_ as the latest release for the Go1.

The unitree_legged_sdk is used to control their legged robots either onboard the robot or remotely.
It communicates with the main controller board on the robot either via UDP within the robot, or via UDP over a network.

*   See the Go1 Unitree Legged SDK Manual in :doc:`Downloads <../downloads>` and the :ref:`Controlling Unitree Robots with the unitree_legged_sdk<label-unitree-videos-unitree-legged-sdk>` for details on using the SDK.
*   See the `unitree_legged_sdk/comm.h`_ header for possible commands and feedback messages over UDP.
*   See the demo applications for example usage in `C++`_ and `Python`_.


.. _`v3.8.0`: https://github.com/unitreerobotics/unitree_legged_sdk/tree/v3.8.0
.. _`C++`: https://github.com/unitreerobotics/unitree_legged_sdk/tree/v3.8.0/example
.. _`Python`: https://github.com/unitreerobotics/unitree_legged_sdk/tree/v3.8.0/example_py
.. _`unitree_legged_sdk/comm.h`: https://github.com/unitreerobotics/unitree_legged_sdk/blob/v3.8.0/include/unitree_legged_sdk/comm.h
