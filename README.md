# gazebo_tricycle_plugins

gazebo_tricycle_plugins is Gazebo plugins for tricycle driving.

## Built with

- ROS Noetic under Ubuntu 20.04 LTS

------

## Getting Started

### Installation

``` $ sudo apt-get install ros-noetic-gazebo-ros-pkgs ros-noetic-gazebo-ros-control ros-noetic-ros-controllers```
    
``` $ sudo apt-get install -y libgazebo11-dev```
    
``` $ sudo apt-get install -y gazebo11```

### How to using a gazebo_mecanum_plugins into xacro file.

``` bash
  <gazebo>
    <!--Modified
    plugin:-->
    <plugin name="tricycle_drive_controller" filename="libTricycleDriveModPlugin.so">
      <rosDebugLevel>Debug</rosDebugLevel>
      <robotNamespace>${NS}</robotNamespace>
      <publishWheelTF>false</publishWheelTF>
      <publishWheelJointState>true</publishWheelJointState>
      <steeringJoint>front_steering_joint</steeringJoint>
      <actuatedWheelJoint>front_wheel_joint</actuatedWheelJoint>
      <actuatedWheelDiameter>${FRONT_WHEEL_RADIUS*2}</actuatedWheelDiameter>
      <encoderWheelLeftJoint>left_wheel_joint</encoderWheelLeftJoint>
      <encoderWheelRightJoint>right_wheel_joint</encoderWheelRightJoint>
      <encoderWheelDiameter>${BACK_WHEEL_RADIUS*2}</encoderWheelDiameter>
      <encoderWheelSeparation>${BACK_WHEEL_BASELINE}</encoderWheelSeparation>
      <commandTopic>cmd_vel</commandTopic>
      <odometryTopic>odom</odometryTopic>
      <odometryFrame>odom</odometryFrame>
      <odometrySource>encoder</odometrySource>
      <robotBaseFrame>base_footprint</robotBaseFrame>
      <updateRate>10.0</updateRate>
      <wheelspeed>0.5</wheelspeed>
      <wheelAcceleration>0.3</wheelAcceleration>
      <wheelDeceleration>0.3</wheelDeceleration>
      <wheelSpeedTolerance>0.05</wheelSpeedTolerance>
      <wheelTorque>20</wheelTorque>
      <steeringSpeed>1.3</steeringSpeed>
      <steeringAngleTolerance>0.02</steeringAngleTolerance>
      <steeringAngleLimit>${M_PI/2}</steeringAngleLimit>
    </plugin>
  </gazebo>
```
------