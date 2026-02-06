# FΛVI AIR v1.0.0 — Release (FΛVI AIR for GPS-denied autonomy)

**FΛVI AIR is the primary aerial node of the FΛVI network, bridging the gap between digital intelligence and physical autonomy.**

This marks the official launch of FΛVI AIR, an autonomous aerial platform designed for GPS-denied indoor environments. This release establishes the core architecture for Physical AI-driven flight and real-time industrial telemetry.

# FΛVI AIR is a silent, secure, and self-flying indoor agent that provides real-time eyes on your most critical infrastructure, even in areas where GPS and humans can't easily go.

<img width="1920" height="1080" alt="Screenshot (219)" src="https://github.com/user-attachments/assets/4f482a54-666d-43b9-ba62-1579756e411d" />

<img width="1920" height="1080" alt="Screenshot (218)" src="https://github.com/user-attachments/assets/613cf7f8-7de2-45c6-a80a-947e00fc9b81" />

---

## ## **Key Features**

* **FΛVI CORE Logic:** Initial implementation of the "Agentic Brain" for state management (Idle, Patrol, Emergency).
* **Physical AI Navigation:** Modular framework for SLAM 4.0 and 360° LiDAR sensor fusion.
* **Cyan-Carbon Dashboard:** A high-fidelity React interface for real-time telemetry via WebSockets.
* **Stealth Mode:** Integrated logic for ultra-silent operation (**<45dB** target) in sensitive environments.

---

## ## **Technical Architecture**

* **OS:** ROS 2 Jazzy Jalisco (Ubuntu 24.04) support.
* **Communication:** Secure WebSocket bridge between the on-board Physical AI and the Command Center.
* **Safety:** Hard-coded "Kill-Switch" protocols and local-first data encryption for industrial security.

---

## ## **Installation**

To access the live deployment, visit the application link below:
**[Launch FΛVI AIR Dashboard](https://www.google.com/search?q=https://2b53801f-ca1b-4f85-98c0-0ae46c570eef-00-2vfj6k128lygq.picard.replit.dev)**

### **CLI Setup (Local Environment)**

1. **Update System & Install Dependencies**
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y python3-colcon-common-extensions git

```


2. **Clone the Repository**
```bash
git clone https://github.com/your-repo/favi-air.git
cd favi-air

```


3. **Initialize the Agentic Brain**
```bash
source /opt/ros/jazzy/setup.bash
colcon build --packages-select favi_core
source install/setup.bash

```


4. **Launch the Node**
```bash
ros2 launch favi_air physical_ai_launch.py

```



---

## ## **Configuration**

### **LiDAR Sensor Fusion Parameters**

To fine-tune the spatial awareness and obstacle detection, modify the `fusion_config.yaml` located in the `favi_core/config/` directory.

| Parameter | Type | Default | Description |
| --- | --- | --- | --- |
| `scan_range_max` | float | `12.0` | Maximum distance (meters) for LiDAR detection. |
| `fusion_weight_lidar` | float | `0.85` | Confidence weight for LiDAR vs IMU data. |
| `voxel_grid_size` | float | `0.05` | Resolution of the 3D map point cloud. |
| `collision_buffer` | float | `0.3` | Safety radius (meters) maintained around the node. |

---

## ## **Troubleshooting**

If you encounter issues during deployment, check the common ROS 2 error fixes below:

### **1. Package Not Found**

**Error:** `package 'favi_core' not found`

* **Fix:** Ensure you have sourced your local workspace after building.
```bash
source install/setup.bash

```



### **2. Middleware (DDS) Issues**

**Error:** Nodes cannot see each other or `ros2 topic list` is empty.

* **Fix:** Check your `ROS_DOMAIN_ID`. Ensure all components are on the same ID (default is 0).
```bash
export ROS_DOMAIN_ID=0

```



### **3. Permission Denied (Serial/USB)**

**Error:** Cannot connect to LiDAR or MCU via USB.

* **Fix:** Add your user to the `dialout` group to access serial ports.
```bash
sudo usermod -a -G dialout $USER

```



### **4. Build Failures**

**Error:** `colcon build` fails due to missing dependencies.

* **Fix:** Use `rosdep` to install all required system dependencies automatically.
```bash
rosdep install -i --from-path src --rosdistro jazzy -y

```



---

**Developed by:** FΛVI
