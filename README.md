# Arduino-Robot-arm-V2-installation
  This repository will cover the steps taken to install a different version of the Arduino arm which is shown below. Unlike the previous Arm which was a complete a package and only required to install the package, this one was not. This repistory is a continuation of the previous one and depends on it. If you haven't installed the previous arm then go to this link and do so.  https://github.com/Kalal0/Arduino-Robot-Arm-installation
  
  
  Arduino Arm V2: 
 
 ![image](https://user-images.githubusercontent.com/109832303/184187166-0af1afa2-59e8-461e-a58f-33ba5e8b35ae.png)



## Installation steps: 

1 - Download the required 3D modeling files (.stl) from here: https://drive.google.com/drive/folders/18E0vgwkuOhObBcaOVkfFNj-FnycijkbE

    You can ignore the .c4d files they aren't usable with Gazebo or Rviz. There are 7 .stl files, The first 6 represent different parts 
    of the Robot Arm with the the entire robot arm being the 7th. For more information refer to end of the document for a 
    more thorough explanation.
    
</br>
    
2 - Now the idea is that the Old Aruino Arm will be used as a base instead of starting from scratch. First things first backup the old Arm so that if anything
goes wrong you can go back to the start. goto  <sup> catkin_*workspace name* </sup>
