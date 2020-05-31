##  0.readme

- [ref](https://github.com/IntelRealSense/librealsense/issues/2215)


我做了一些工作，并制作了一个直接使用rosbag API读取bag文件的类。它实现了以下功能:

- 1.每当调用nextFrame函数时，读取一个bag文件并异步输出一对rgb和depth帧。该类不使用realsense管道，而是解析rosbag消息，因此不会丢失任何帧

- 2.由于AFAIK在设备上的rgb和深度流之间没有硬件同步，因此该类检查时间戳并输出时间上最接近的rgb和深度文件对（无需昂贵的搜索）。

- 3.返回的深度框与摄影机的视点对齐

- 4.深度帧另存为xml，每个像素的完整浮点值以米为单位

- 5.该类与帧一起输出rosbag中记录的每个帧的帧号和时间戳（根据系统时钟）

- 6.如果您要进行某些几何处理，还可以保存两个传感器的本征矩阵和本征矩阵

该代码应易于阅读，并且依赖项包括opencv 3.x，glog，librealsense，以及ros库中包含为标头和boost的部分。文件print_helpers.cpp / h是rosbag查看器工具示例中包含的文件的修改版本。

即使您不直接使用该类，您也应该能够将这些方法复制并粘贴到该类中，以根据需要读取rosbag。
