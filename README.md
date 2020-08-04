ros2_thetav
============================

ROS2 node to publish image topic from RICOH THETA V on Ubuntu18.04 ROS2-Dashing.
This is **unofficial** package.

This node publish sensor_msgs/msg/Image topic named "thetav", the format is RGB8.


## Build
1. Install GStreamer-1.0.
```
$ sudo apt-get install libgstreamer1.0-0 gstreamer1.0-plugins-base gstreamer1.0-plugins-good gstreamer1.0-plugins-bad gstreamer1.0-plugins-ugly gstreamer1.0-libav gstreamer1.0-doc gstreamer1.0-tools gstreamer1.0-x gstreamer1.0-alsa gstreamer1.0-gl gstreamer1.0-gtk3 gstreamer1.0-qt5 gstreamer1.0-pulseaudio
```

2. Build and install richoapi/libuvc-theta.
```
$ git clone https://github.com/ricohapi/libuvc-theta.git
$ cd libuvc-theta
$ mkdir build
$ cd build
$ cmake ..
$ make && sudo make install
```

3. Clone this repository, and build.
```
$ cd ~/ros2_ws/src
$ git clone https://github.com/itsuka-to/ros2_thetav.git
$ cd ~/ros2_ws
$ colcon build --symlink-install
$ . install/setup.bash
```

## Run 
1. Check that your ThetaV is Live-Streaming-Mode, and run!
```
$ ros2 run ros2_thetav thetav_publisher
```

2. If you want to check image outputs, launch rviz2.
```
# another terminal
$ cd ~/ros2_ws
$ . install/setup.bash
$ rviz2
```

And "Add" -> "By topic" -> "/thetav -> Image"

## Reference
### ricohapi/libuvc-theta-sample
This package use the library which is including this sample code.

https://github.com/ricohapi/libuvc-theta-sample

### richoapi/libuvc-theta
https://github.com/ricohapi/libuvc-theta