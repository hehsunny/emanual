### 1. Overview
This chapter explains one of basic OP3 demos; action.  
OP3 will play sequence of pre-defined actions while speaking.

### 2. Getting started
#### 2.1 Usage
 > Reference : [How to execute Default Demo]


### 3. ROS API
The followings are ROS APIs used only in action demo.

#### 3.1 Subscribed Topics
`/robotis/open_cr/button"`([std_msgs/String]{: .popup})

&emsp;&emsp; This message processes button maneuver.


#### 3.2 Published Topics
`/robotis/enable_ctrl_module`([std_msgs/String]{: .popup})

&emsp;&emsp; This message configures control modules to operate ROBOTIS-OP3.  

`/robotis/action/page_num`([std_msgs/Int32]{: .popup})
&emsp;&emsp; This message transfers page number to action_module to play specific actions.  

`/play_sound_file`([std_msgs/String]{: .popup})
&emsp;&emsp; This message contains the path of voice files for speaking.


#### 3.3 Services
`/robotis/action/is_running`([op3_action_module_msgs/IsRunning]{: .popup})  
&emsp;&emsp; This service checks whether the action is running or not.  


### 4. Parameters
`action_script` (string, default : "~/op3_demo/script/action_script.yaml")  
&emsp;&emsp; This yaml file contains list of action and audio file bundles.

<br>[&lt;&lt; Back]

[std_msgs/String]: /docs/en/popup/std_msgs_string/
[std_msgs/Int32]: /docs/en/popup/std_msgs_int32_message/
[How to execute Default Demo]:OP3_How_to_execute_Default_Demo.md
[op3_action_module_msgs/IsRunning]: /docs/en/popup/op3_IsRunning.srv/
[&lt;&lt; Back]:[op3_demo.md]
