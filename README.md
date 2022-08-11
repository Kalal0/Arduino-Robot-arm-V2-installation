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
    
6 - Open the .urdf file using a text editor and replace everything with the below piece of code: 

    <?xml version="1.0" ?>
<!-- created with Phobos 1.0.1 "Capricious Choutengan" -->
<robot name="arduino_robot_arm">
    <link name="base">
        
<inertial>
            <origin xyz="0 0 0" rpy="0 0 0" />
            <mass value="0.01" />
            <inertia ixx="0.001" ixy="0" ixz="0" iyy="0.001" iyz="0" izz="0.001" />
        </inertial>

        <visual name="Base">
               <origin xyz="-0.26 0 0" rpy="0 0 0" />
            <geometry>
                <mesh filename="package://robot_arm_pkg/meshes/stl/1.stl" scale="0.00098 0.00098 0.00098" />
            </geometry>
        </visual>
        <collision name="Base">
            <origin xyz="-0.0029 0.00016 0.01165" rpy="3.14159 0 0" />
            <geometry>
                <cylinder radius="0.0592" length="0.05469" />
            </geometry>
        </collision>
    </link>
    <link name="waist">
        
<inertial>
            <origin xyz="0 0 0" rpy="0 0 0" />
            <mass value="0.001" />
            <inertia ixx="0.001" ixy="0" ixz="0" iyy="0.001" iyz="0" izz="0.001" />
        </inertial>

        <visual name="Waist">
                <origin xyz="-0.26 0 0" rpy="0 0 0" />
            <geometry>
                <mesh filename="package://robot_arm_pkg/meshes/stl/2.stl" scale="0.00098 0.00098 0.00098" />
            </geometry>
        </visual>
        <collision name="Waist.000">
                <origin xyz="0 0 0" rpy="0 0 0" />
            <geometry>
                <mesh filename="package://robot_arm_pkg/meshes/stl/2.stl" scale="0.00098 0.00098 0.00098" />
            </geometry>
        </collision>
    </link>
    <link name="arm1">
        
<inertial>
            <origin xyz="0 0 0" rpy="0 0 0" />
            <mass value="0.001" />
            <inertia ixx="0.001" ixy="0" ixz="0" iyy="0.001" iyz="0" izz="0.001" />
        </inertial>

        <visual name="Arm 01">
             <origin xyz="-0.15 0 -0.2" rpy="0 0 0" />
            <geometry>
                <mesh filename="package://robot_arm_pkg/meshes/stl/3.stl" scale="0.00098 0.00098 0.00098" />
            </geometry>
        </visual>
        <collision name="Arm 01">
               <origin xyz="0 0 0" rpy="0 0 0" />
            <geometry>
                <box size="0.04221 0.16277 0.02051" />
            </geometry>
        </collision>
    </link>
    <link name="arm2">
        
<inertial>
            <origin xyz="0 0 0" rpy="0 0 0" />
            <mass value="0.001" />
            <inertia ixx="0.001" ixy="0" ixz="0" iyy="0.001" iyz="0" izz="0.001" />
        </inertial>

        <visual name="Arm 02">
                <origin xyz="-0.55 0.05 -0.4" rpy="0 0 0" />
            <geometry>
                <mesh filename="package://robot_arm_pkg/meshes/stl/4.stl" scale="0.00098 0.00098 0.00098" />
            </geometry>
        </visual>
        <visual name="arm3">
               <origin xyz="-0.55 0.05 -0.4" rpy="0 0 0" />
            <geometry>
                <mesh filename="package://robot_arm_pkg/meshes/stl/5.stl" scale="0.00098 0.00098 0.00098" />
            </geometry>
        </visual>
        <collision name="Arm 02">
               <origin xyz="0 0 0" rpy="0 0 0" />
            <geometry>
                <box size="0.02681 0.16397 0.0384" />
            </geometry>
        </collision>
    </link>
    <link name="gripper">
        
<inertial>
            <origin xyz="0 0 0" rpy="0 0 0" />
            <mass value="0.001" />
            <inertia ixx="0.001" ixy="0" ixz="0" iyy="0.001" iyz="0" izz="0.001" />
        </inertial>

        <visual name="Gripper">
            <origin xyz="-0.015 0 -0.35" rpy="0 0 0" />
            <geometry>
                <mesh filename="package://robot_arm_pkg/meshes/stl/6.stl" scale="0.00098 0.00098 0.00098" />
            </geometry>
        </visual>
        <collision name="Gripper.000">
               <origin xyz="0 0 0" rpy="0 0 0" />
            <geometry>
                <mesh filename="package://robot_arm_pkg/meshes/stl/6.stl" scale="0.00098 0.00098 0.00098" />
            </geometry>
        </collision>
    </link>
    
    <joint name="base_joint" type="revolute">
         <origin xyz="0 0 0" rpy="0 0 0" />
        <parent link="base" />
        <child link="waist" />
        <axis xyz="0 0 1.0" />
        <limit lower="-1.571" upper="1.571" effort="1000.0" velocity="1.0" />
    </joint>
    <joint name="shoulder" type="revolute">
      <origin xyz="-0.07 0.07 0.2" rpy="0 0 -0.8" />
        <parent link="waist" />
        <child link="arm1" />
        <axis xyz="0 1.0 0" />
        <limit lower="-1.571" upper="0.36" effort="1000.0" velocity="1.0" />
    </joint>
    <joint name="elbow" type="revolute">
<origin xyz="0.42 -0.05 0.2" rpy="0 0 0.1" />
        <parent link="arm1" />
        <child link="arm2" />
        <axis xyz="0 1.0 0" />
        <limit lower="0" upper="1.57" effort="1000.0" velocity="1.0" />
    </joint>
    <joint name="wrist" type="revolute">
        <origin xyz="-0.55 0.05 -0.05" rpy="0 0 0" />
        <parent link="arm2" />
        <child link="gripper" />
        <axis xyz="0 1.0 0" />
        <limit lower="-1.57" upper="1.57" effort="1000.0" velocity="1.0" />
    </joint>
    
<transmission name="trans_base_joint">
        <type>transmission_interface/SimpleTransmission</type>
        <joint name="base_joint">
            <hardwareInterface>hardware_interface/PositionJointInterface</hardwareInterface>
        </joint>
        <actuator name="base_joint_motor">
            <hardwareInterface>hardware_interface/PositionJointInterface</hardwareInterface>
            <mechanicalReduction>1</mechanicalReduction>
        </actuator>
    </transmission>
    <transmission name="trans_shoulder">
        <type>transmission_interface/SimpleTransmission</type>
        <joint name="shoulder">
            <hardwareInterface>hardware_interface/PositionJointInterface</hardwareInterface>
        </joint>
        <actuator name="shoulder_motor">
            <hardwareInterface>hardware_interface/PositionJointInterface</hardwareInterface>
            <mechanicalReduction>1</mechanicalReduction>
        </actuator>
    </transmission>
    <transmission name="trans_elbow">
        <type>transmission_interface/SimpleTransmission</type>
        <joint name="elbow">
            <hardwareInterface>hardware_interface/PositionJointInterface</hardwareInterface>
        </joint>
        <actuator name="elbow_motor">
            <hardwareInterface>hardware_interface/PositionJointInterface</hardwareInterface>
            <mechanicalReduction>1</mechanicalReduction>
        </actuator>
    </transmission>
    <transmission name="trans_wrist">
        <type>transmission_interface/SimpleTransmission</type>
        <joint name="wrist">
            <hardwareInterface>hardware_interface/PositionJointInterface</hardwareInterface>
        </joint>
        <actuator name="wrist_motor">
            <hardwareInterface>hardware_interface/PositionJointInterface</hardwareInterface>
            <mechanicalReduction>1</mechanicalReduction>
        </actuator>
    </transmission>
    <gazebo>
        <plugin name="gazebo_ros_control" filename="libgazebo_ros_control.so">
            <robotNamespace>/</robotNamespace>
        </plugin>
    </gazebo>
</robot>

    
