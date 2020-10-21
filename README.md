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


## Creating ROS Publisher and Subscriber in Python
