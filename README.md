<img src="docs/assets/logo.png" width="120" alt="LIV-eye logo" align="left"/>
<h1>LIV-Eye-with-RTK: A Low-Cost LiDAR-Inertial-Visual-RTK Fusion 3D Sensor for Robotics and Embodied AI


<p align="center">
<a href="LICENSE"><img alt="Software License" src="https://img.shields.io/badge/Software-GPLv2-blue"></a>
<a href="LICENSES/HARDWARE-CERN-OHL-S-2.0.txt"><img alt="HW License" src="https://img.shields.io/badge/Hardware-CERN--OHL--S--2.0-green"></a>
<a href="LICENSES/DOCS-CC-BY-4.0.txt"><img alt="Docs License" src="https://img.shields.io/badge/Docs-CC%20BY%204.0-yellow"></a>
</p>

<!-- # 🚀 Interested in Embodied AI? Explore the UMI-3D Ecosystem

<div align="center">

<h3>
  🌐 <a href="https://umi-3d.github.io/">UMI-3D Project Homepage</a>
</h3>

<table>
  <tr>
    <td align="center" width="33%">
      <a href="https://github.com/Physical-Intelligence-Laboratory/UMI-3D-Hardware">
        <b>🔧 UMI-3D Hardware</b>
      </a>
    </td>
    <td align="center" width="33%">
      <a href="https://github.com/hku-mars/UMI-3D">
        <b>🛰️ UMI-3D SLAM Pipeline</b>
      </a>
    </td>
    <td align="center" width="33%">
      <a href="https://github.com/Physical-Intelligence-Laboratory/UMI-3D-Policy">
        <b>🤖 UMI-3D Policy</b>
      </a>
    </td>
  </tr>

  <tr>
    <td align="center">
      <a href="https://github.com/Physical-Intelligence-Laboratory/UMI-3D-Hardware">
        <img src="docs/assets/nav_hardware.jpg" width="100%" alt="UMI-3D Hardware"/>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/hku-mars/UMI-3D">
        <img src="docs/assets/nav_processing.jpg" width="100%" alt="UMI-3D SLAM Pipeline"/>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/Physical-Intelligence-Laboratory/UMI-3D-Policy">
        <img src="docs/assets/nav_policy.jpg" width="100%" alt="UMI-3D Policy"/>
      </a>
    </td>
  </tr>

  <tr>
    <td align="center">
      Hardware design, BOM, CAD, 3D-print parts
    </td>
    <td align="center">
      SLAM, synchronization, calibration, and data processing
    </td>
    <td align="center">
      Policy training, deployment, inference<br><br>
      <a href="https://github.com/Physical-Intelligence-Laboratory/UMI-3D-Dataset">
        <b>📦 Dataset & Models</b>
      </a>
    </td>
  </tr>
</table>

</div>

--- -->

## Table of Contents
- [Repository Structure](#repository-structure)
- [Bill of Materials (BOM)](#bill-of-materials-bom)
- [Assembly](#assembly)
- [Driver Installation and Run](#driver-installation-and-run)
- [LiDAR-Camera Joint Calibration](#lidar-camera-joint-calibration)
- [Running FAST-LIVO2](#running-fast-livo2)
- [Acknowledgements](#acknowledgements)
- [License](#license)

---

<!-- ## Highlights
> **One sentence summary**: A ~¥5000 (≈ $700) fully open-source hardware/software LiDAR-Inertial-Visual fusion perception kit. ⚙️ Easy assembly, no soldering, one-click reproducibility. 🐳 Supports ROS1/ROS2 and Docker, 🧭 full calibration workflow (intrinsic/extrinsic/time sync), 🧰 compatible with FAST-LIVO2 algorithms, and delivers colored point cloud and odometry results in just 5 minutes. -->

<!-- --- -->

## Repository Structure
```text
├── FAST-LIVO2-Mid360-Config - The configuration and launch files of FAST-LIVO2 for the Mid-360 LiDAR
├── liv_eye_cad - Solidworks files for LIV-Eye
├── livox_ros_driver2 - Livox LiDAR ROS driver
├── mvs_ros_driver - Hikvision Camera ROS driver
├── Handsfree_RTK_ROS - Handsfree_RTK ROS driver
├── rtk_connect - Solidworks files for RTK Connector
└── README.md - Project homepage
└── ...
```

---

## Bill of Materials (BOM)

> Target total cost: ≈ ¥5,000 (≈ $700, subject to actual purchase)

| Category | Model/Name | Reference Price | Image |
|----------|------------|-----------------|-------|
| LiDAR    | [Livox Mid-360](https://www.livoxtech.com/cn/mid-360) | ¥3999 (≈ $560) | <img src="docs/assets/lidar.png" alt="MID-360" width="120px"> |
| Camera   | [Hikvision MV-CU013-A0UC](https://www.hikrobotics.com/cn/machinevision/productdetail/?id=12628) | ¥700 (≈ $100) | <img src="docs/assets/camera.png" alt="Camera" width="120px"> |
| RTK   | [T-RTK UM982 Mobile Dual-Antenna](https://e.tb.cn/h.8QbOG9jPHEXBjJs?tk=WvO9TX06NBA) | ¥1500 (≈ $215) | <img src="docs/assets/rtk.jpg" alt="Camera" width="120px"> |
| Lens     | [Hikvision MVL-HF0628M-6MPE](https://www.hikrobotics.com/en/machinevision/productdetail/?id=4871) | ¥150 (≈ $20) | <img src="docs/assets/lens.png" alt="Lens" width="120px"> |
| Wire     | [FAST-LIVO2-RTK Hardware Synchronizer](https://e.tb.cn/h.88xnROGMKfDRI6h?tk=l21jTX0qGV2) | ¥800 (≈ $105) | <img src="docs/assets/sync_rtk.jpg" alt="Sync" width="120px"> |
| Battery  | [12V DC Battery](https://detail.tmall.com/item.htm?id=657166348854) | ¥99 (≈ $15) | <img src="docs/assets/battery.png" alt="Battery" width="120px"> |

---

## Assembly

Solidworks CAD files are provided in [liv_eye_cad](./liv_eye_cad).  
You can download and use them for 3D printing and assembly:

<p align="center">
  <img src="docs/assets/solidworks.gif" alt="Solidworks" width="45%"/>
  <img src="docs/assets/device.jpg" alt="Device" width="40%"/>
</p>

---

<!-- ## Wiring

The diagram below shows the complete wiring of **LIV-Eye**, in just six steps:

<p align="center">
  <img src="docs/assets/connect.jpg" alt="Wiring diagram" width="80%">
</p>

> **Note**  
> If you do not need to use the LiDAR-Camera hardware synchronizer, please refer to the connection method and STM32 hardware synchronization solution in [LIV_handhold](https://github.com/xuankuzcr/LIV_handhold).

--- -->

## Driver Installation and Run

1. Download and install [MVS](https://connecthkuhk-my.sharepoint.com/:u:/g/personal/zhengcr_connect_hku_hk/Ed0Xq17d6udNqYn4vkR71bQBFz0z6_Kru3cz1gD95FIgrQ?e=FPvfkT) and [Livox-SDK2](https://github.com/Livox-SDK/Livox-SDK2). Set the camera to *trigger mode* in MVS.

2. Install the camera ROS driver [mvs_ros_driver](./mvs_ros_driver) and launch in trigger mode:
```bash
roslaunch mvs_ros_driver mvs_camera_trigger.launch 
```

3. Install and launch the LiDAR ROS driver [livox_ros_driver2](./livox_ros_driver2):
```bash
roslaunch livox_ros_driver2 msg_MID360.launch
```

4. Install and launch the RTK ROS driver [Handsfree_RTK_ROS](./Handsfree_RTK_ROS):
```bash
roslaunch handsfree_rtk handsfree_rtk.launch
```

4. Record sensor data:
```bash
rosbag record /livox/lidar /livox/imu /left_camera/image
```

> **Note**  
> The [mvs_ros_driver](./mvs_ros_driver) and [livox_ros_driver2](./livox_ros_driver2) are the same as those in [LIV_handhold](https://github.com/xuankuzcr/LIV_handhold), and include modifications to support millisecond-level hardware synchronization.

---

## LiDAR-Camera Joint Calibration

1. Calibrate camera intrinsics. e.g. [matlab](https://ustc-flicar.github.io/calibration/index#cameras).
2. Use [FAST-Calib](https://github.com/hku-mars/FAST-Calib) for LiDAR–camera extrinsic calibration.

<p align="center">
  <img src="docs/assets/33.jpg" alt="camera calibration" width="44%"/>
  <img src="docs/assets/fast_calib.jpg" alt="fast calib" width="45%"/>
</p>

---

## Running FAST-LIVO2

Install [FAST-LIVO2](https://github.com/hku-mars/FAST-LIVO2). The configuration and launch files for the Mid-360 are provided in [FAST-LIVO2-Mid360-Config](./FAST-LIVO2-Mid360-Config). Update the intrinsic and extrinsic parameters to match your device, then run:
```bash
roslaunch fast_livo mapping_mid360.launch
```

This demo corresponds to the example LIV-Eye rosbag, which can be downloaded [here](https://pan.baidu.com/s/1bs9hSF9BD0LZFTiiEkNLeg?pwd=2zr5).
<p align="center">
  <img src="docs/assets/livo.jpg" alt="livo2 results" width="100%">
</p>

---

<!-- ## Platform Adaptability

**LIV-Eye is compact yet versatile!** With its small form factor, standardized wiring, and open-source software, it can be seamlessly integrated into a wide range of robotic platforms to enable perception, navigation, and embodied AI research.

<p align="center">
  <img src="docs/assets/mobile.jpg" alt="LIV-Eye on wheeled robot" width="40%"/>
  <img src="docs/assets/platform.jpg" alt="fast calib" width="53%"/>
</p> -->


## Acknowledgements

This project is based on the following open-source projects:  

- Driver and time synchronization: [LIV_handhold](https://github.com/xuankuzcr/LIV_handhold)  
- Calibration method: [FAST-Calib](https://github.com/hku-mars/FAST-Calib)  
- Algorithm: [FAST-LIVO2](https://github.com/hku-mars/FAST-LIVO2)  
- CAD Design: [Link](https://github.com/hku-mars/FAST-LIVO2/issues/119) by [pcl5](https://github.com/pcl5)
---

## License

The source code is released under the GPLv2 license.  

If you use this codebase in academic research, please cite any of the following papers:

```
[1] Zheng, Chunran, et al. "FAST-LIVO2: Fast, Direct LiDAR-Inertial-Visual Odometry." 
[2] Zheng, Chunran, et al. "FAST-LIVO: Fast and Tightly-coupled Sparse-Direct LiDAR-Inertial-Visual Odometry." 
[3] Zheng, Chunran, et al. "FAST-Calib: LiDAR-Camera Extrinsic Calibration in One Second." 
[4] Ziming, Wang, et al. "USTC FLICAR: A sensors fusion dataset of LiDAR-inertial-camera for heavy-duty autonomous aerial work robots." 
```
