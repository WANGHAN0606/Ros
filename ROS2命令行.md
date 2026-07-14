打开终端

#### cd
+ 语法：cd <目录路径>
+ 功能：改变工作目录。若没有指定“目录路径”，则回到用户的主目录
#### pwd
+ 语法：pwd
+ 功能：此命令显示出当前工作目录的绝对路径
#### mkdir
+ 语法：mkdir [选项] <目录名称>
+ 功能：创建一个目录/文件夹
#### ls
+ 语法：ls [选项] [目录名称…]
+ 功能：列出目录/文件夹中的文件列表
#### gedit
+ 语法：gedit <文件名称>
+ 功能：打开gedit编辑器编辑文件，若没有此文件则会新建
#### mv
+ 语法：mv [选项] <源文件或目录> <目地文件或目录>
+ 功能：为文件或目录改名或将文件由一个目录移入另一个目录中
#### cp
+ 语法：cp [选项] <源文件名称或目录名称> <目的文件名称或目录名称>
+ 功能：把一个文件或目录拷贝到另一文件或目录中，或者把多个源文件复制到目标目录中
#### rm
+ 语法：rm [选项] <文件名称或目录名称…>
+ 功能：该命令的功能为删除一个目录中的一个或多个文件或目录，它也可以将某个目录及其下的所有文件及子目录均删除。对于链接文件，只是删除了链接，原有文件均保持不变
#### sudo
+ 语法：sudo [选项] [指令]
+ 功能：以系统管理员权限来执行指令
## 例子
### 小海龟转弯
#### 运行结点程序
+ ros2 run
> ros2 run turtlesim turtlesim_node
 ros2 run turtlesim turtle_teleop_key
#### 查看节点信息
+ 查看都有哪些节点
  ros2 node list
+ 查看详细信息
  ros2 node info
  >ros2 node info /turtlesim 
#### 查看话题信息
+ ros2 topic list
+ 查看消息数据
   ros2 topic echo /
   >ros2 topic echo /turtle1/pose 
#### 发布话题消息
>ros2 topic pub --rate 1 /turtle1/cmd_vel geometry_msgs/msg/Twist "{linear: {x: 2.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 1.8}}"
#### 发布服务请求
> ros2 service call /spawn turtlesim/srv/Spawn "{x: 2, y: 2, theta: 0.2, name: ''}"
#### 发送动作目标
>ros2 action send_goal /turtle1/rotate_absolute turtlesim/action/RotateAbsolute "theta: 3"
#### 录制控制命令
+ rosbag
  > ros2 bag record /turtle1/cmd_vel
 ros2 bag play rosbag2_2022_04_11-17_35_40/rosbag2_2022_04_11-17_35_40_0.db3