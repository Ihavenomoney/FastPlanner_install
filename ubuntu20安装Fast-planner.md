# 一、配置mobarxterm连接到ubuntu20
1、先配置ssh，使用mobarxterm链接到ubuntu20虚拟机

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753942349734-35cdcecf-982f-4252-92bc-a69a79b7e035.png)

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753942449456-7d9acfc5-f5b0-4c19-83b1-ba79de4ef201.png)

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753942475784-10c47b99-5637-4004-8824-303c56ed7e5d.png)

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753942502280-b40ce958-213d-44cb-bef7-d1587531281c.png)

2、使用mobarxterm链接到虚拟机

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753942572404-9c255c5f-7c93-473a-96f8-3f8732c911a2.png)

# 二、上传两个源码包
1、把nlopt、Fast-Planner的源码包上传到虚拟机

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753942715482-210a4420-ab2f-44db-90eb-23d2048c2090.png)

# 三、安装ROS
1、使用鱼香ROS安装脚本先安装ROS Noetic

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753942803562-8ee12e66-bca5-48e7-ae01-02b077d1126f.png)

2、按1

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753942839292-8e1276c7-e26b-4188-b95c-d7dea3cf875a.png)

3、按1

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753942861781-6c2e54d1-1fc2-4cdd-ab8d-ea70e0e50948.png)

4、按2

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753942890562-53c7ac93-8453-4f4c-b125-304573442652.png)

5、按3

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753942978764-c6f41f25-9ecf-4b88-98df-c73b8bffe306.png)

6、按1，这一步之后只需要等待安装完成即可

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753943008467-fec4de34-08af-41ba-b528-961ba53c96b2.png)

安装成功

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753943402886-e1f6675a-8625-4362-83d8-0135f4940487.png)



![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753943464742-26c98727-067f-4be7-9f0d-a2e80c3d2cad.png)

# 四、安装nlopt2.7.1
1、根据其主页提示，这里需要先安装nlopt2.7.1

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753943543706-e6af9942-842a-4981-8274-8129e2275bd3.png)

2、由于访问github clone 有问题，所以只能使用前边步骤上传的源码包

解压nlopt包

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753943641382-e517c91f-e6f7-4652-8570-4bef99072d1b.png)

3、执行下面两条命令

```plain
mkdir build
cd build
```

4、执行下面命令

```plain
cmake ..
```

5、根据提示是因为cmake版本太低了，我们需要编译安装一个高版本的。

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753943744612-e43e4805-abff-4ef6-8899-ace7bee83106.png)

6、上传cmake源码包到虚拟机

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753943793275-a07429e1-3802-44bf-a021-ff919b7ce624.png)

7、根据下面的步骤来编译安装cmake3.22.1，这个过程会比较漫长，我的虚拟机大概得运行20-30分钟

```plain
tar xzf cmake-3.22.1.tar.gz
cd cmake-3.22.1
#装openssl
sudo apt-get install libssl-dev -y
sudo apt-get install libgl1-mesa-dev -y
./configure
make
sudo make install
sudo cmake --version
```

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753943862048-4a07b5fa-9247-445a-8ca1-142c90d93e43.png)

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753943890958-f97eda84-8d7a-4e45-ab00-72cf66932422.png)

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753943924649-09abbd10-95b5-4cea-bb19-7e5ba15784cb.png)

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753943975023-bd3ccce7-6794-4c0a-9c88-008fb669d2cd.png)

./configure运行完是下面的样子

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753944484916-a9e0e3e7-a1fc-48cf-8098-dc065de0782e.png)

执行make是这个样子

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753944535028-41e5e007-be6e-4839-a498-9310359408ec.png)

make执行完是这个样子

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753945128698-6b6e50af-5a5c-4dcc-89bd-723f6285628a.png)

执行sudo make install 

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753945182331-f293d50a-76a2-4bac-9f71-403480f7616b.png)

执行sudo cmake --version查看版本号，可以看到已经成功安装

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753945235047-3b9f205c-0f3b-4bce-8157-d1fb7d938225.png)

# 五、开始安装nlopt
1、重新返回nlopt的build目录下

```plain
cd /home/xiaoming/nlopt-master/build/
```

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753945366499-87013bcb-4cde-4c44-b364-b325f99cface.png)

2、执行cmake ../ 会报错，前边加个sudo就可以

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753945402041-91336a2a-8042-4aa7-80ff-6d2b8410226a.png)

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753945440097-2a4564b9-2955-465f-be71-842b71520713.png)

3、执行make，这个时候会报权限错误，加个sudo 就没事

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753945496783-f7206dc4-e79a-45d7-8e42-2ce2508490ad.png)

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753945525274-674300f5-3a43-4d96-827b-c85dbc8555af.png)

4、执行sudo make install

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753945562117-bae90ae4-ea17-4be9-83b2-e825437f5029.png)

5、您可以运行以下命令来安装其他所需的工具：

```plain
sudo apt-get install libarmadillo-dev
```

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753945666777-0043b6a3-b667-4364-b59b-ff271acb6538.png)

# 六、工作空间
1、这个时候我们需要初始化一个工作空间

（1）创建并初始化工作空间

```plain
# 创建目录结构
mkdir -p ~/catkin_ws/src

# 进入src目录
cd ~/catkin_ws/src

# 初始化工作空间
catkin_init_workspace
```

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753945949643-b2b7fd21-edaa-4fc5-9242-47c2bef93103.png)

（2）构建工作空间

```plain
# 返回工作空间根目录
cd ~/catkin_ws/

# 构建工作空间
catkin_make
```

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753945979280-da30a3d4-49a0-4c35-8db5-e01f22fd6fe7.png)

（3）配置环境变量

```plain
# 临时添加到当前终端会话
source ~/catkin_ws/devel/setup.bash

# 永久添加到bashrc文件（推荐）
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753946016428-6fcbb592-c531-4a5d-956c-575b3a184461.png)

2、进入/home/xiaoming/catkin_ws/src

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753946081377-eb96f92d-edd8-4f35-accc-cd7b244e9ea2.png)

3、把用户目录的压缩包剪切过来

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753946133183-ffaa0d61-b99b-4ddd-86cd-cfb46c455653.png)

# 七、开始安装Fastplaner的步骤
1、解压这个安装包

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753946158416-a2142230-c61b-4fd6-9cb5-7d986ac3144b.png)

2、把zip包删除，然后把解压好的文件夹改个名字【个人习惯】

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753946287490-b5774e0f-d16d-409e-a9ec-4a73e250556d.png)

3、执行

```plain
cd ../
```

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753946338881-1af464ad-a4f6-4d40-9d1a-377b1dcbb530.png)

4、执行【这个时候肯定会报错】

```plain
catkin_make
```

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753946376346-3554d7ec-4695-432a-a353-8f934255c312.png)

5、开始频繁报错

（1）第一次报错，说是PCL需要至少c++14版本

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753947039462-79b46d67-35e0-44ea-beb6-2764b3ceba01.png)

```plain
catkin_make -DCMAKE_CXX_STANDARD=14 -DCMAKE_CXX_STANDARD_REQUIRED=ON
```

Tip：按照github主页给的教程，如果只执行catkin_make，就会报错需要更高版本的C++，执行上边那个就可以一遍过了。

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753949955280-edb74cae-0b98-4fbc-a87a-802347c12c22.png)

# 八、最终演示
1、此时我们返回虚拟机，新建两个终端。

（1）执行下面的命令调用可视化界面

```plain
source devel/setup.bash && roslaunch plan_manage rviz.launch
```

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753950332502-e4835356-ebb3-4965-8aab-d4d8d9b53bba.png)

Tip：执行后会有个报错弹窗，看大概意思是对ROS1的支持到期了，关掉它暂时不用管。

（2）开始模拟

```plain
source devel/setup.bash && roslaunch plan_manage kino_replan.launch
```

在第二个终端执行后，就可以看到界面有变化了。

![](https://cdn.nlark.com/yuque/0/2025/png/25434171/1753950433970-74b238f6-4b45-4702-ae40-a330012be155.png)

