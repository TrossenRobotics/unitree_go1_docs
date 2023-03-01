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
