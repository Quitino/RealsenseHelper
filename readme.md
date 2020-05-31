##  0.readme



- [0.深度信息处理](https://github.com/juniorxsound/ThreadedDepthCleaner)

Threaded depth-map cleaning and inpainting using OpenCV.

- [1.rosbag reader](https://github.com/IntelRealSense/librealsense/issues/2215)

I worked on it a little bit and I made a class that reads bag files using directly the rosbag API. It implements the following functionalities

> 1.Reads a bag file and outputs a pair of rgb and depth frames asynchronously whenever the function nextFrame is called. The class does not use the realsense pipeline, rather it parses the rosbag messages, so there are no frames dropped

> 2.Since AFAIK there is no hardware synchronization between rgb and depth streams on the device, the class checks the timestamps and outputs the pair of rgb and depth files that are closest in time (without expensive searches).

> 3.The depth frame returned is aligned to the camera point of view

> 4.Depth frame is saved as an xml with the full floating point values in meters for each pixel

> 5.Together with the frames, the class outputs the frame number and the timestamp for each frame recorded in the rosbag (according to the system clock)

> 6.It also saves the intrinsic and extrinsic matrices for both sensors in case you want to do some geometry


##  1.realsense examples

- [ref0.realsense examples](https://github.com/IntelRealSense/librealsense/tree/master/examples)
- [ref1.t265](https://github.com/IntelRealSense/librealsense/blob/master/doc/t265.md)
- [ref2.tracking-and-depth](https://github.com/IntelRealSense/librealsense/tree/master/examples/tracking-and-depth)
