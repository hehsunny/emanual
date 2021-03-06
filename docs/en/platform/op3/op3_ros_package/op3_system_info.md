### 1. Overview
System Configuration of ROBOTIS-OP3  

![](/assets/images/platform/op3/op3_system_configuration.png)

### 2. Main Controller(PC)
 - Specification  
  Intel NUC i3, 8GB RAM, 128GB M.2 SSD, WLAN  
   > Reference : [Intel NUC]

 - OS  
   Linux Mint 18.1 Xfce
   > Reference : [User Guides]

 - [Robot Operating System(ROS)]
   Version :  Kinetic  
   > Reference : [What is ROS?]


### 3. Camera

![](/assets/images/platform/op3/hd-pro-webcam-c920-feature-image.png)

  * Model  
    Logitech C920

  * Supported Resolution
    - 640 * 480  
    - 800 * 600  
    - 1920 * 1080  


  > Reference : [Logitech support specification]


### 4. U2D2  
  > Reference : [e-Manual | Not yet ready]()  


### 5. OpenCR  
  OpenCR is a sub-controller for ROBOTIS-OP3  
  OpenCR is managing sensor interfaces and power distribution(3-axis Gyro, 3-axis Accelerometer)
  > Reference : [OpenCR H/W Specification]


### 6. XM430-W350-R  
  XM430-W350-R is a DXL Protocol 2.0 based X-series Actuator  
  > Reference : [e-Manual]


[&lt;&lt; Back](op3_user's_guide.md)

[Intel NUC]:https://www.intel.com/content/www/us/en/products/boards-kits/nuc/kits.html
[User Guides]:https://www.linuxmint.com/documentation.php
[What is ROS?]:http://www.ros.org/about-ros/
[Robot Operating System(ROS)]:op3_robot_operating_system.md
[Logitech support specification]:http://support.logitech.com/en_ca/product/hd-pro-webcam-c920/specs
[OpenCR H/W Specification]:https://github.com/ROBOTIS-GIT/OpenCR/wiki/Hardware_Specification  
[e-Manual]:http://support.robotis.com/en/techsupport_eng.htm#product/actuator/dynamixel_x/xm_series/xm430-w350.htm  
