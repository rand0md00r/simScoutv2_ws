# simScoutv2_ws

1.下载

    #根目录下
    
    git clone https://github.com/rand0md00r/simScoutv2_ws.git

2.编译
    
    cd simScoutv2_ws/
    catkin_make
    
3.启动虚拟scout底盘+单线激光雷达+相机
    
    source devel/setup.bash 
    roslaunch scout_gazebo_sim scout_empty_world.launch

4.报错解决
4.1 [spawn_model-4] process has died    模型生成错误
    解决方法：
    
        sudo gedit /usr/lib/python2.7/xml/etree/ElementTree.py

加入以下代码：

        import sys
        import re
        import warnings
        reload(sys)                                                 #添加
        sys.setdefaultencoding("utf-8")        #添加


引自：https://blog.csdn.net/jiaostyle/article/details/123033225
