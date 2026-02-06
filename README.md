# FΛVI AIR v1.0.0 — Initial Release (FΛVI AIR for GPS-denied autonomy)
FΛVI AIR is the primary aerial node of the FΛVI network, bridging the gap between digital intelligence and physical autonomy.

This marks the official launch of FΛVI AIR, an autonomous aerial platform designed for GPS-denied indoor environments. This release establishes the core architecture for Physical AI-driven flight and real-time industrial telemetry.

<img width="1920" height="1080" alt="Screenshot (219)" src="https://github.com/user-attachments/assets/cdb280fc-10fa-4f41-bc5c-e6384f84aad0" /> <img width="1920" height="1080" alt="Screenshot (218)" src="https://github.com/user-attachments/assets/f81d5c62-c3f8-4179-bc81-bc5860aae49e" />

## Key Features
FΛVI CORE Logic: Initial implementation of the "Agentic Brain" for state management (Idle, Patrol, Emergency).

Physical AI Navigation: Modular framework for SLAM 4.0 and 360° LiDAR sensor fusion.

Cyan-Carbon Dashboard: A high-fidelity React interface for real-time telemetry via WebSockets.

Stealth Mode: Integrated logic for ultra-silent operation (<45dB target) in sensitive environments.

## Technical Architecture
OS: ROS 2 Jazzy Jalisco (Ubuntu 24.04) support.

Communication: Secure WebSocket bridge between the on-board Physical AI and the Command Center.

Safety: Hard-coded "Kill-Switch" protocols and local-first data encryption for industrial security.

## Installation
To access the live deployment, visit the application link below: 
Launch FΛVI AIR Dashboard : https://2b53801f-ca1b-4f85-98c0-0ae46c570eef-00-2vfj6k128lygq.picard.replit.dev/

CLI Setup (Local Environment)
To set up the FΛVI AIR environment on your local machine, follow these steps:

Update System & Install Dependencies

Bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y python3-colcon-common-extensions git
Clone the Repository

Bash
git clone https://github.com/your-repo/favi-air.git
cd favi-air
Initialize the Agentic Brain

Bash
source /opt/ros/jazzy/setup.bash
colcon build --packages-select favi_core
source install/setup.bash
Launch the Node

Bash
ros2 launch favi_air physical_ai_launch.py

Developed by: FΛVI 


