========================
Getting Started with ROS
========================

This guide is intended to help users get started using the Go1 EDU using ROS.

Requirements
============

*   A basic understanding of ROS 1
*   A computer running Linux Ubuntu 18.04
*   ROS 1 Melodic

Software Packages
=================

The following packages are used to control the robot using ROS.
Version ``v3.8.0`` of the unitree_legged_sdk and the unitree_ros_to_real repositories are the latest compatible versions with the Go1 EDU.

*   `unitree_legged_sdk`_ — `v3.8.0 <https://github.com/unitreerobotics/unitree_legged_sdk/releases/tag/v3.8.0>`_
*   `unitree_ros_to_real`_ — `v3.8.0 <https://github.com/unitreerobotics/unitree_ros_to_real/releases/tag/v3.8.0>`_
*   `unitree_ros`_

.. _`unitree_legged_sdk`: https://github.com/unitreerobotics/unitree_legged_sdk
.. _`unitree_ros_to_real`: https://github.com/unitreerobotics/unitree_ros_to_real
.. _`unitree_ros`: https://github.com/unitreerobotics/unitree_ros

unitree_legged_sdk
------------------

Unitree's SDK used to control their legged robots either onboard the robot or remotely.

unitree_ros_to_real
-------------------

Do low or high-level control of the Go1 EDU using ROS.

unitree_ros
-----------

ROS Gazebo simulation and description packages for Unitree's legged robots.

.. attention::

    The simulation does not currently support high-level control and only allows for the low-level joint control.

Workspace Setup
===============

Clone/download the packages and their required versions to your catkin workspace.

.. code-block:: console

    $ mkdir -p catkin_ws/src # 'catkin_ws' can be anything
    $ cd catkin_ws/src
    $ git clone https://github.com/unitreerobotics/unitree_legged_sdk -b v3.8.0
    $ git clone https://github.com/unitreerobotics/unitree_ros_to_real -b v3.8.0
    $ git clone https://github.com/unitreerobotics/unitree_ros

Build the workspace.

.. code-block:: console

    $ cd catkin_ws/src
    $ catkin_make

Source the devel space to configure your terminal's environment to find packages, launch files, executables, etc.

.. code-block:: console

    $ source ~/catkin_make/devel/setup.bash

The above command can be added to the end of the ``~/.bashrc`` file to configure every new terminal opened.

Running an Example
==================

The following steps demonstrate basic usage of the Unitree packages using high-level control.

.. attention::

    During this demo, the robot will walk around.
    Make sure nothing is in the robot's way.

**Terminal 1**:
Launch the high-level UDP connection node.

.. code-block:: console

    $ roslaunch unitree_legged_real real.launch ctrl_level:=highlevel

**Terminal 2**:
Launch the example_walk demo.
Observe the robot as it moves around.

.. code-block:: console

    $ rosrun unitree_legged_real example_walk

Running the state_sub demo subscribes to the robot's state and gets feedback from the robot.

.. code-block:: console

    rosrun unitree_legged_real state_sub
