# 第一个demo

## 主要读取图片，然后将图片输出到另一个图片文件中

## 在的docker中运行时，可能出现引用文件不存在（使用的docker环境中opencv的版本为4.5.3）：
1,在CMakeLists.txt文件中加入target_link_libraries( one_demo ${OpenCV_LIBS} /usr/local/lib/libopencv_highgui.so.4.5.3) 这一行;
2,需要将/usr/local/include/opencv4目录下的opencv2文件夹移动到/usr/local/include/，
3,cmake运行之前，如果build文件中存在已经编译的文件，可能要删除build文件中的所有文件，再重新编译