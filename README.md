# Turtlebot3-with-SLAM
المهمة الثانية لتدريب الاساليب الذكية

خطوات تنفيذ المهمة

اولا:

نثبت الباكجات الخاصة ب (تورتال بوت3) باستعمال الاكواد التالية

	$ sudo apt-get install ros-melodic-dynamixel-sdk
	$ sudo apt-get install ros-melodic-turtlebot3-msgs
	$ sudo apt-get install ros-melodic-turtlebot3

ثانيا:

 نعمل نسخ للباكج الخاص ب(تورتال بوت3) داخل ورك سبيس باستعمال الاكواد التالية

	$ cd ~/catkin_ws/src/
	$ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
	$ cd ~/catkin_ws && catkin_make\
	
![image](https://user-images.githubusercontent.com/85806841/124514372-8b584800-dde5-11eb-961d-86a8ac633e43.png)

ثالثا:
نشغل الخريطة ب(غازيبو) باستعمال الاكواد التالية

	$ export TURTLEBOT3_MODEL=burger
	$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
	
![image](https://user-images.githubusercontent.com/85806841/124514581-09b4ea00-dde6-11eb-9c02-f8ed9e02509f.png)

و من ثم نشغله في (موف ات) باستعمال الاكواد التالية

	$ export TURTLEBOT3_MODEL=burger
	$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
	
![image](https://user-images.githubusercontent.com/85806841/124515351-eab75780-dde7-11eb-925f-d1f3d96c1625.png)

رابعا:
وفي النهاية نحتاج لحفظ الخريطة باستعمال الكود

	$ rosrun map_server map_saver -f ~/map
	
