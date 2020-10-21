# ros_baxter_workshop
This repository contains information for getting started with ROS and Baxter robot. This repository assumes that you have a working Ubuntu OS.


## Prerequisites
* [Ubuntu 14.04 LTS](http://releases.ubuntu.com/14.04/)


## ROS Indigo and Baxter API Installation
* ROS Indigo can be installed by following the official wiki page [here](http://wiki.ros.org/indigo/Installation/Ubuntu). However, the Baxter API website contains the same procedure. Therefore, users can follow the Baxter API website, as mentioned in the next point.
* The Baxter API website is [here](https://sdk.rethinkrobotics.com/wiki/Workstation_Setup).


## Installations of Python packages using pip
`pip` is the package installer for Python. Below are the steps to install `pip`, `ipython`, and `jupyter`-

```
sudo apt install python-pip
sudo pip install --upgrade pip
sudo pip install --upgrade ipython
sudo pip install --upgrade jupyter
```

## Basics of Python required for ROS
Minimal introduction to Python (version 2.7).

### Defining a variable
```
i = 0
name = "Ravi"
price = 1.5
correct = True
```

### Loops
```
# repeat print statement 10 times or print 10 numbers starting from 0
for i in range(10):
    print i
```

### List
A `list` is a powerful container to store various objects.
```
fruits = ["apple", "mango", "orange"]
fruits.append("grape")
```

A minimal introduction is presented above. Users are strongly advised to read further!


## Creating a ROS Package
Use `catkin_create_pkg` command to create a ROS package.
```
cd ros_ws/src
catkin_create_pkg hello_ros rospy roscpp
```
Please follow the official ROS wiki page for future study [here](http://wiki.ros.org/ROS/Tutorials/CreatingPackage).


## Creating ROS Publisher and Subscriber in Python
Publishers and subscribers are the backbones of the ROS framework. In the following subsections, we will create a publisher and subscriber for string datatype.

### Creating a ROS Publisher
```
import rospy
from std_msgs.msg import String

def publisher():
    pub = rospy.Publisher("my_ros_topic", String, queue_size=10)
    rospy.init_node("publisher")
    rate = rospy.Rate(10) # 10hz
    index = 0 
    while not rospy.is_shutdown():
        hello_str = "hello world %d" % index
        print hello_str
        pub.publish(hello_str)
        rate.sleep()
        index += 1

if __name__ == "__main__":
    try:
        publisher()
    except rospy.ROSInterruptException:
        pass
```

### Creating a ROS Subscriber
```
import rospy
from std_msgs.msg import String

def callback(data):
    print data
    
def listener():
    rospy.init_node("listener")
    rospy.Subscriber("my_ros_topic", String, callback)
    rospy.spin()

if __name__ == "__main__":
    listener()
```

Please follow the official ROS wiki page for future study [here](http://wiki.ros.org/ROS/Tutorials/WritingPublisherSubscriber%28python%29).

