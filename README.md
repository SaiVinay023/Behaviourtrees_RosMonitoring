# **Behaviourtrees_rosmonitoring**

## Instructions to Implement Behaviour Trees and ROS Monitoring

### **Prerequisites**
- ROS 2 Humble
- `behaviortree_cpp_v3` library
- Groot (for visualizing behavior trees)

### **Installation Steps**

1. **Clone the Repository:**

   Open a terminal and execute the following commands:

   ```bash
   mkdir -p ~/ros_ws/src
   cd ~/ros_ws/src
   git clone <current_repo_url>
   cd ~/ros_ws
   colcon build
   ```

2. **Run the Behavior Tree:**

   ```bash
   ros2 run bt_bumpgo bt_bumpgo_main
   ros2 run groot Groot  # Start Groot for visualization
   ```

   In Groot:
   - Select `Monitor` -> `Start` -> `Connect Local` to visualize the behavior tree graph.

### **Implementing ROS Monitoring**

1. **Clone the ROSMonitoring Package:**

   Clone the ROSMonitoring package from the repository:

   ```bash
   cd ~/
   git clone https://github.com/autonomy-and-verification-uol/ROSMonitoring.git
   cd ROSMonitoring
   git checkout ros2
   ```

2. **Create a Simple Offline Monitor:**

   - Copy the offline configuration file from the current repository to the ROSMonitoring repository.
   - The ROSMonitoring repository does not need to be in your ROS workspace; it can be executed separately.

   ```bash
   cd ~/ROSMonitoring/generator/ros2_devel/
   chmod +x generator
   python3 ./generator --config_file offline_config.yaml
   ```

### **To Resolve Build Errors**

If you encounter any errors, follow these steps in your `ros_ws`:

```bash
rm -rf build install log
source /opt/ros/humble/setup.bash
colcon build
```

### **Launching the Monitoring Tools**

1. **Start the ROS Monitoring Tool:**

   In a terminal, run:

   ```bash
   cd ~/ros_ws/
   . install/setup.bash
   ros2 launch src/monitor/launch/monitor.launch
   ```

2. **Run the Instrumented Launch File:**

   In another terminal, execute:

   ```bash
   cd ~/ros_ws/
   . install/setup.bash
   ros2 launch src/Bump-and-Go-with-Behavior-Trees/launch/run_instrumented.launch
   ```

   Or use:

   ```bash
   ros2 launch src/Bump-and-Go-with-Behavior-Trees/launch/run_launch.py
   ```

### **Output**

- A `log.txt` file will be generated in your repository directory.

---

You can copy and paste this content directly into the README file on GitHub to provide a clean, organized set of instructions.
