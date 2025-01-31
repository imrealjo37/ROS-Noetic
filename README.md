# تثبيت ROS Noetic و ROS2 Humble

## 1. تثبيت ROS Noetic على Ubuntu 20.04

### **الخطوات:**

1. **إعداد المصادر وإضافة المفتاح**
   ```bash
   sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
   sudo apt install curl # إذا لم يكن مثبتًا مسبقًا
   curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.key | sudo apt-key add -
   ```

2. **تحديث الحزم وتثبيت ROS Noetic الكامل**
   ```bash
   sudo apt update
   sudo apt install ros-noetic-desktop-full
   ```

3. **تهيئة بيئة ROS**
   ```bash
   echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
   source ~/.bashrc
   ```

4. **تثبيت أدوات إضافية**
   ```bash
   sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
   sudo rosdep init
   rosdep update
   ```

## 2. تثبيت ROS2 Humble على Ubuntu 22.04

### **الخطوات:**

1. **إعداد المصادر وإضافة المفتاح**
   ```bash
   sudo apt update && sudo apt install -y curl gnupg lsb-release
   sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key | sudo apt-key add -
   sudo sh -c 'echo "deb http://packages.ros.org/ros2/ubuntu $(lsb_release -cs) main" > /etc/apt/sources.list.d/ros2-latest.list'
   ```

2. **تحديث الحزم وتثبيت ROS2 Humble الكامل**
   ```bash
   sudo apt update
   sudo apt install ros-humble-desktop
   ```

3. **تهيئة بيئة ROS2**
   ```bash
   echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
   source ~/.bashrc
   ```

4. **تثبيت أدوات إضافية**
   ```bash
   sudo apt install -y python3-colcon-common-extensions
   ```

## 3. التأكد من التثبيت الصحيح

### **للتحقق من ROS Noetic:**
```bash
roscore
```

### **للتحقق من ROS2 Humble:**
```bash
ros2 doctor
```

