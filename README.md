# Project: RCETI Endotracheal Tube Robot (Forked)

This is a fork of my original team project for OSU CSE Capstone (Spring 2025).
The `main` branch contains the preserved course submission.


<!-- 
The `enhanced` branch contains personal improvements made after the course:
- Improved ROS2 launch configuration
- Better documentation
- Rewritten URDF & gazebo plugin cleanup
- Added simulation video walkthrough
- etc...
-->

Original commit history is preserved for academic integrity.



## For Setup of Ubuntu Machine (For Connection with Raspberry Pi)

### Setting Up Static IP
- Open Settings > Network.
- Click on Wired Connection (the Ethernet interface).
- Click Settings (⚙️).
- Go to the IPv4 tab.
- Select Manual and set:
- Address: 192.168.2.1
- Netmask: 255.255.255.0
- Gateway: Leave blank
- Click Apply and disconnect/reconnect Ethernet.

### Setting Up ROS to use static IP
Enter the following commands into your terminal in Ubuntu 22.04

`echo "export ROS_DOMAIN_ID=7" >> ~/.bashrc ` \
`echo "export ROS_IP=$(hostname -I | awk '{print $1}')" >> ~/.bashrc` \
`echo "export ROS_HOSTNAME=$(hostname -I | awk '{print $1}')" >> ~/.bashrc` \
`source ~/.bashrc` \

This should set up your ROS IP so that it can talk with the Raspberry Pi

### Running RCETI System
- Build your workspace (outside of project directory)
```colcon build```
- source workspace (outside of project directory)
```source install/setup.bash```
- run the launch files inside of RCETI deployment package
```ros2 launch rceti_deployment rceti_deployment.launch.xml```

