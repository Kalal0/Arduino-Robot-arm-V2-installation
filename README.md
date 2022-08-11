# Arduino-Robot-arm-V2-installation
  This repository will cover the steps taken to install a different version of the Arduino arm which is shown below. Unlike the previous Arm which was a complete a package and only required to install the package, this one was not. This repistory is a continuation of the previous one and depends on it. If you haven't installed the previous arm then go to this link and do so.  https://github.com/Kalal0/Arduino-Robot-Arm-installation
  
  
  Arduino Arm V2: 
 
 ![image](https://user-images.githubusercontent.com/109832303/184187166-0af1afa2-59e8-461e-a58f-33ba5e8b35ae.png)



## Installation steps: 

1 - Download the required 3D modeling files (.stl) from here: https://drive.google.com/drive/folders/18E0vgwkuOhObBcaOVkfFNj-FnycijkbE

<sub>You can ignore the .c4d files they aren't usable with Gazebo or Rviz. There are 7 .stl files, The first 6 represent different parts 
    of the Robot Arm with the the entire robot arm being the 7th. The 7th won't be used in this tutorial, however, you can open it using blender to get an idea
  on how the the entire robot is supposed to look when constructed. 
</sub>
    
</br>

2 - Now the idea is that the Old Aruino Arm will be used as a base instead of starting from scratch. First things first backup the old Arm so that if anything
goes wrong you can go back to the start. </br> 

    catkin_**workspace name** -> src -> arduni_robot_arm  
</br>   
and copy the robot_arm_pkg file somewhere else.
</br></br>

3 - Now go to:

    catkin_**workspace name** -> src -> arduni_robot_arm - > robot_arm_pkg -> meshes - > stl
    
4 - Delete all the files then add the 6 .stl files downloaded from step 1.
![image](https://user-images.githubusercontent.com/109832303/184194780-867b14d1-9dbc-4aa0-8a02-b073b3bb59c4.png)

5 - Now go to

    catkin_**workspace name** -> src -> arduni_robot_arm - > robot_arm_pkg -> urdf
    
6 - Open the .urdf file using a txt editor and replace it's content with the following: 


   [document.txt](https://github.com/Kalal0/Arduino-Robot-arm-V2-installation/files/9310677/document.txt)
   
7 - Now you're done all that's left is to remake the catkin file and run Rviz. Open the cmd and input the following commands: 

    1 - cd catkin_*workspace name*
    2 - catkin_make
    3 - source /home/*user name*/catkin_*workspace name*/devel/setup.bash
    4 - roslaunch robot_arm_pkg check_motors.launch

Change the workspace name and user name tags accordingly.

8 - And that's it you can now view the new robot Arm in Rviz and move it freely using the joint state publisher.




    
