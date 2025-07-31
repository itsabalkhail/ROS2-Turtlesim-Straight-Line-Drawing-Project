# ROS2 Turtlesim Straight Line Drawing Project 🐢

## Project Description
This project demonstrates how to use ROS2 and Turtlesim to draw a straight white line by controlling the default turtle. The project has been successfully implemented and the required objective achieved.

## What Was Successfully Accomplished ✅
- Installed and configured ROS2 working environment
- Successfully launched Turtlesim simulator
- Controlled the turtle using keyboard input
- **Drew a clear white straight line** as shown in the screenshot

![Final Result](turtle-straight-line.png)

## Prerequisites

### Operating System
- Ubuntu 20.04 LTS or 22.04 LTS
- Desktop Environment
- Internet connection for installation

### Required Software
- ROS2 (Humble Hawksbill recommended)
- Python 3.8+
- Terminal/Command Line

## Installation and Setup Steps

### Step 1: Install ROS2

#### Add ROS2 Sources
```bash
# Update system
sudo apt update && sudo apt upgrade -y

# Add GPG key
sudo apt install curl gnupg lsb-release
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg

# Add repository
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```

#### Install ROS2
```bash
# Update package list
sudo apt update

# Install ROS2 Desktop (full version)
sudo apt install ros-humble-desktop -y

# Install additional tools
sudo apt install ros-dev-tools -y
```

### Step 2: Configure Environment
```bash
# Add ROS2 to bashrc for automatic sourcing
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc

# Source ROS2 in current session
source /opt/ros/humble/setup.bash
```

### Step 3: Install Turtlesim
```bash
# Install turtlesim package
sudo apt install ros-humble-turtlesim -y

# Verify installation
ros2 pkg list | grep turtlesim
```

### Step 4: Test Installation
```bash
# Test ROS2
ros2 --help

# Check version
ros2 --version
```

## Project Implementation - Drawing the Straight Line

### Step 1: Launch Turtlesim
Open terminal and run:
```bash
ros2 run turtlesim turtlesim_node
```

**Expected Result:**
- A blue window will appear with a green turtle in the center
- If the window doesn't appear, check your desktop environment

### Step 2: Launch Keyboard Control
In a new terminal (without closing the first one):
```bash
ros2 run turtlesim turtle_teleop_key
```

**Messages that will appear:**
```
Reading from keyboard
---------------------------
Use arrow keys to move the turtle.
'q' or 'Q' to quit.
```

### Step 3: Draw the Straight Line
1. **Click on the second terminal** to ensure it's active
2. **Use one arrow key only** in one direction (e.g., right arrow →)
3. **Press repeatedly** in the same direction
4. **Watch the turtle** draw a white straight line

### Final Result ✅
- Clear white straight line on blue background
- Turtle positioned at the end of the line
- Proof of successful control and drawing

## Commands Used in the Project

### Basic Commands
```bash
# Launch simulator
ros2 run turtlesim turtlesim_node

# Launch control
ros2 run turtlesim turtle_teleop_key

# Stop programs
Ctrl + C
```

### Monitoring and Diagnostic Commands
```bash
# Show active nodes
ros2 node list

# Show topics
ros2 topic list

# Monitor turtle position
ros2 topic echo /turtle1/pose

# Show node information
ros2 node info /turtlesim
```

## Common Issues and Solutions

### Issue 1: Turtlesim Window Doesn't Appear
**Cause:** Display environment problem
**Solution:**
```bash
# Check DISPLAY variable
echo $DISPLAY

# If empty, set it
export DISPLAY=:0
```

### Issue 2: "Package not found"
**Cause:** ROS2 not sourced
**Solution:**
```bash
source /opt/ros/humble/setup.bash
```

### Issue 3: Turtle Doesn't Move
**Cause:** Terminal not active
**Solution:** Make sure to click on the terminal containing turtle_teleop_key

### Issue 4: Line is Broken or Not Straight
**Cause:** Irregular key pressing
**Solution:** Press one key regularly at a consistent speed

## Project Technical Specifications

### System Information
- **ROS2 Distribution:** Humble Hawksbill
- **Node Type:** turtlesim_node
- **Control Method:** teleop_twist_keyboard
- **Drawing Method:** Turtle trail/path

### Parameters Used
- **Starting Position:** Center (5.5, 5.5)
- **Line Color:** White
- **Movement Speed:** Default teleop speed
- **Direction:** User-controlled via arrow keys

