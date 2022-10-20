# Steps to create a ROS Node
In this section we will learn how to create a ROS Node inside pkg_ros_basics ROS Package which we created in the previous section.

1. Navigate to pkg_ros_basics.
```
cd ~/catkin_ws/src/pkg_ros_basics
```
OR
```
roscd pkg_ros_basics
```
NOTE: roscd will work only if you have sourced setup.bash of your catkin workspace.


2. Create a scripts folder for your Python scripts and navigate into the folder.
```
mkdir scripts
cd scripts
```
3. Create a Python script called node_hello_ros.py.
```
touch node_hello_ros.py
```
4. Open the script in any text editor and start editing.
```
gedit node_hello_ros.py
```
or if you have any code editor like vsCode or vim you can use that too.

5. The First line of all your Python ROS scripts should be the following `shebang`:
```
#!/usr/bin/env python3
```
The #! shebang is used to tell the kernel which interpreter should be used to run the commands present in the file.

6. Now write a ROS Node to print `Hello World!` on the console.
```bash 
#!/usr/bin/env python3

import rospy

def main():    
    
    rospy.init_node('node_hello_ros', anonymous=True)
    rospy.loginfo("Hello World!")
    rospy.spin()

if __name__ == '__main__':
    try:
        main()
    except rospy.ROSInterruptException:
        pass
 ```

7. Now you have to make this script executable.
```
chmod +x node_hello_ros.py
```
8. Now in order to run your ROS Node,

Open up a terminal and run ROS Master.
```
roscore
```
9. Once the roscore is up running, open a new termminal and run the ROS Node.
```
rosrun pkg_ros_basics node_hello_ros.py
```
NOTE: This command will work only if you have sourced setup.bash of your catkin workspace either manually or using .bashrc.


You should get some output like this,
```
[INFO] [1601277063.968749]: Hello World!
```
