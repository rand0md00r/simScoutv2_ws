# simScoutv2_ws
#ubuntu18.04 melodic

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

        import sys                             #原有
        import re                              #原有
        import warnings                        #原有
        reload(sys)                            #添加
        sys.setdefaultencoding("utf-8")        #添加


引自：https://blog.csdn.net/jiaostyle/article/details/123033225

5.更改部署配置

5.1更改urdf模型

维护scout/scout_description/urdf/ 文件夹，urdf文件包含结构如下：

    combination.xacro
        ├inertial.xacro                         <!--惯性矩阵计算模块-->
        ├scout_v2.xacro                     <!--底盘模块-->
        ├camera.xacro                        <!--相机模块-->
        ├sensor_camera.xacro        <!--相机感知模块-->
        ├VLP-16.urdf.xacro                <!--16线激光雷达模块-->
        ├laser.xacro                              <!--单线激光雷达--><!--备选-->
        ├sensor_laser.xacro              <!--单线激光雷达--><!--备选-->
    
5.2 更改世界地图

更改世界urdf模型，维护scout/scout_gazebo_sim/worlds/weston_robot_empty.world

更改launch文件，维护scout/scout_gazebo_sim/launch/scout_empty_world.launch

5.3
