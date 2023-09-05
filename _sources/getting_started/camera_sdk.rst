==================
Unitree Camera SDK
==================

This guide is intended to help users get started using the Go1 EDU using the `Unitree Camera SDK`_.

The Unitree Camera SDK allows depth and color streaming, and provides intrinsic calibration information. The library also offers pointcloud, depth image aligned to color image.

.. _`Unitree Camera SDK`: https://github.com/unitreerobotics/UnitreecameraSDK

Dependencies
============

.. list-table::
    :header-rows: 1
    :align: center

    * - Dependency
      - Minimum Version
      - Remarks
    * - OpenCV
      - >=4
      - Requires GStreamer
    * - CMake
      - >=2.8
      -
    * - OpenGL
      -
      - For Pointcloud GUI
    * - GLUT
      -
      - For Pointcloud GUI
    * - X11
      -
      - For Pointcloud GUI

Workspace Setup
===============

1.  Clone the repository.

    .. code-block:: console

        $ git clone https://github.com/unitreerobotics/UnitreecameraSDK.git

2.  Build the SDK.

    .. code-block:: console

        $ cd UnitreeCameraSDK
        $ mkdir build
        $ cd build
        $ cmake ..
        $ make

Running Examples
================

.. note::

  You may have to kill processes that occupy the cameras' resources before running the examples.
  To do so, run the commands given in the `example_putImagetrans demo`_.

  .. code-block:: console

    # If you start this file, you must bash "kill.sh" to turn off automatic startup program.
    # "Unitree/autostart/02camerarosnode/kill.sh" and "Unitree/autostart/04imageai/kill.sh".
    # You can also use the following instructions:

    ps -A | grep point | awk '{print $1}' | xargs kill -9
    ps -aux|grep mqttControlNode|grep -v grep|head -n 1|awk '{print $2}'|xargs kill -9
    ps -aux|grep live_human_pose|grep -v grep|head -n 1|awk '{print $2}'|xargs kill -9

.. _`example_putImagetrans demo`: https://github.com/unitreerobotics/UnitreecameraSDK/blob/ecd2058ba3f033af11c2d2a0306b44cc8d819332/examples/example_putImagetrans.cc#L43-L48

Get Camera Raw Image
--------------------

.. code-block:: console

    $ cd UnitreeCameraSDK
    $ ./bin/example_getRawFrame

Get Calibration Parameters File
-------------------------------

.. code-block:: console

    $ cd UnitreeCameraSDK
    $ ./bin/example_getCalibParamsFile

Get Rectified Image
-------------------

.. code-block:: console

    $ cd UnitreeCameraSDK
    $ ./bin/example_getRectFrame

Get Depth Image
---------------

.. code-block:: console

    $ cd UnitreeCameraSDK
    $ ./bin/example_getDepthFrame

Get Point Cloud
---------------

.. code-block:: console

    $ cd UnitreeCameraSDK
    $ ./bin/example_getPointCloud

Transfer Image to Other Devices
-------------------------------

.. code-block:: console

    $ cd UnitreeCameraSDK
    $ ./bin/example_putImagetrans

Get Image From Other Devices
----------------------------

.. code-block:: console

    $ cd UnitreeCameraSDK
    $ ./bin/example_getimagetrans
