==========
Legged SDK
==========

This guide is intended to help users get started using the Go1 EDU using the `Unitree Legged SDK`_.

.. note::

    This guide is written with `v3.8.0`_ as the latest release for the Go1.

.. _`Unitree Legged SDK`: https://github.com/unitreerobotics/unitree_legged_sdk/tree/v3.8.0
.. _`v3.8.0`: https://github.com/unitreerobotics/unitree_legged_sdk/tree/v3.8.0

.. contents::
    :local:

Dependencies
============

The following Dependencies are required if using a remote PC to work with the robot.

.. list-table::
    :header-rows: 1
    :align: center

    * - Dependency
      - Minimum Version
    * - `Boost`_
      - >=1.5.4
    * - `CMake`_
      - >=2.8.3
    * - `g++`_
      - >=8.3.0

.. _`Boost`: http://www.boost.org/
.. _`CMake`: http://www.cmake.org/
.. _`g++`: https://gcc.gnu.org/

.. code-block:: console

    $ sudo apt-get install libboost-all-dev cmake g++

Workspace Setup
===============

1.  Clone the repository at the v3.8.0 tag.

    .. code-block:: console

        $ git clone -b v3.8.0 https://github.com/unitreerobotics/unitree_legged_sdk.git

2.  Build the SDK.

    .. code-block:: console

        $ cd unitree_legged_sdk
        $ mkdir build
        $ cd build
        $ cmake ..
        $ make

Running an Example
==================

*   `C++ Legged SDK demos source`_
*   `Python Legged SDK demos source`_

.. _`C++ Legged SDK demos source`: https://github.com/unitreerobotics/unitree_legged_sdk/tree/v3.8.0/example
.. _`Python Legged SDK demos source`: https://github.com/unitreerobotics/unitree_legged_sdk/tree/v3.8.0/example_py

.. tabs::

    .. group-tab:: C++

        .. note::

            Run examples with 'sudo' for memory locking.

        The following steps demonstrate basic usage of the Unitree Legged SDK using high-level control.

        .. attention::

            During this demo, the robot will walk around.
            Make sure nothing is in the robot's way.

        .. code-block:: console

            $ cd unitree_legged_sdk/build
            $ ./example_walk

    .. group-tab:: Python

        .. note::

            For ARM-based platforms, change ``sys.path.append('../lib/python/amd64')`` to ``sys.path.append('../lib/python/arm64')``

        The following steps demonstrate basic usage of the Unitree Legged SDK using high-level control.

        .. attention::

            During this demo, the robot will walk around.
            Make sure nothing is in the robot's way.

        .. code-block:: console

            $ cd unitree_legged_sdk/example_py
            $ python3 example_walk.py
