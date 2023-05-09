About this:
ROS noetic package to visualise UR10 robot

How this was created? 
Created CAD model with Fusion360
Generated ROS1 packages with fusion2urdf [used this branch https://github.com/ruk-shan/fusion2urdf.git]

How does it work?
ModbusReader_MQTTPublisher.py reads the robot data through UR modbus server and publishes to MQTT broker 
MQTTsub_ROSpub.py reads the data from MQTT broker and publishes joint values as ROS topics 
Virtual robot moves based on joint input values   

--------------------------------------------------------------------------------------------------------
How to run: 
Install packages:

http://wiki.ros.org/mqtt_client
    sudo apt install ros-noetic-mqtt-client
MQQT
modbus


Change IP 
setup_config.py

mqttROS_params.yaml
    MQTT broker ip
    
Make sure that you have installed mqtt broker and set the port to 11883
---------------------------------------------------------
Avalable data over MQTT broker 

uncasing_station/UR10/robot_status
    "isPowerOnRobot"
    "isSecurityStopped"
    "isEmergencyStopped"
    "isTeachButtonPressed"
    "isPowerPuttonPressed"

uncasing_station/UR10/joint_angles
    6 robot joint values (in rad)

uncasing_station/UR10/joint_current

uncasing_station/UR10/robot_current

uncasing_station/UR10/joint_temp

uncasing_station/UR10/TCP_pos

--------------------------------------------------------------

Optional Node-Red flow is Avalable in "node-red flow" folder. 
    Import the flow
    install missing modules 
    change ip addresses

