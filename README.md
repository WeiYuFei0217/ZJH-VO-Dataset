# ZJH-VO Dataset

A comprehensive multi-scene and multi-scale benchmark dataset for ground vehicle visual odometry in intelligent transportation systems.

## 📊 Dataset Overview

The ZJH-VO dataset is designed to address the lack of publicly available benchmarks with diversity in scale and scene characteristics for ground vehicle navigation. It provides challenging scenarios across multiple floors of an office complex.

![Dataset Overview](Images/Dataset_Overview.png)
*Data collection vehicle and representative trajectories across four floors (Floor 9, 4, 1, and 0)*

## 🚗 Key Features

- **12 trajectories** across 4 distinct environments
- **12,666 frames** with 8-frame sampling intervals  
- **3,054 meters** of total motion data
- **Ground truth poses** from 2D LiDAR SLAM
- **Multi-camera system** with hardware synchronization
- **Diverse motion patterns** including large rotations and various speeds

## 📁 Dataset Structure

### Environment Characteristics

| Environment | Object Distance | Complexity | BEV Challenge | ITS Application |
|------------|----------------|------------|--------------|-----------------|
| **Dense Office** | Short range | Complex | Large rotations, texture-less walls | Last-mile Delivery |
| **Conference Corridor** | Short-Medium range | Medium | Variable lighting, narrow passages | Service Robots |
| **Outdoor Open-Space** | Long range | Medium | Sparse features, ground-dominant | Campus Navigation |
| **Underground Garage** | Medium range | Simple | Dynamic vehicles, dim lighting | Autonomous Parking |

### Motion Statistics

![Motion Statistics](Images/Motion_Statistics.png)
*Inter-frame motion distributions and trajectory statistics across environments*

- **Inter-frame distances**: 0.00 - 0.31m
- **Inter-frame rotation angles**: 0.00° - 17.70°
- **Motion velocities**: 0.00 - 0.59 m/s

## 🔧 Hardware Configuration
- **Platform**: Four-wheeled mobile robot without suspension
- **Cameras**: 4-camera system with hardware sync
  - Front stereo pair
  - Front-left and front-right cameras
- **Ground Truth**: 2D LiDAR for pose generation

## 📥 Download

The dataset is available in the following formats:

| Component | Size | Link |
|-----------|------|------|
| Full Dataset | ~XXX GB | [Download from BaiduPan](https://pan.baidu.com/xxx) |
| Images Only | ~XXX GB | [Download from BaiduPan](https://pan.baidu.com/xxx) |
| Ground Truth | ~XXX MB | [Download from BaiduPan](https://pan.baidu.com/xxx) |
| Calibration Files | ~XXX MB | [Download from BaiduPan](https://pan.baidu.com/xxx) |

Alternative download links:
- [Google Drive Mirror](https://drive.google.com/xxx)
- [OneDrive Mirror](https://onedrive.live.com/xxx)

## 📂 File Format

```
ZJH-VO/
├── Floor_00/
│   ├── trajectory_01/
│   │   ├── images/
│   │   │   ├── 000000.png
│   │   │   └── ...
│   │   ├── poses.txt
│   │   └── calibration.yaml
│   ├── trajectory_02/
│   └── trajectory_03/
├── Floor_01/
├── Floor_04/
├── Floor_09/
└── README.md
```

### Pose Format
Each line in `poses.txt` contains:
```
timestamp x y z qx qy qz qw
```

### Calibration Format
Camera intrinsics and extrinsics in YAML format compatible with common VO/SLAM frameworks.

## 📊 Benchmark Results

Performance comparison of state-of-the-art methods on ZJH-VO:

| Method | RTE (%) | RRE (°/100m) | APE (m) |
|--------|---------|--------------|---------|
| ORB-SLAM3 | 8.94* | 14.21* | 4.28* |
| DeepVO | 51.95 | 109.11 | 20.06 |
| TartanVO | 10.31 | 17.40 | 5.79 |
| DROID-SLAM | 15.75 | 22.11 | 11.81 |
| BEV-ODOM | 7.28 | 7.98 | 3.95 |
| **BEV-ODOM2** | **3.57** | **4.69** | **2.11** |

*Partial trajectory due to tracking failure

## 📝 Citation

If you use this dataset in your research, please cite:

```bibtex
@article{wei2025bevodom2,
  title={BEV-ODOM2: Enhanced BEV-based Monocular Visual Odometry with PV-BEV Fusion and Dense Flow Supervision for Ground Robots},
  author={Wei, Yufei and Lu, Wangtao and Hu, Chenxiao and Lu, Sha and Han, Fuzhang and Xiong, Rong and Wang, Yue},
  journal={xxx},
  volume={xxx},
  number={xxx},
  pages={xxx},
  year={2025}
}
```

## 🤝 Contributing

We welcome contributions to improve the dataset! Please feel free to:
- Report issues or bugs
- Suggest improvements
- Share your benchmark results
- Contribute evaluation tools

## 📧 Contact

For questions or issues regarding the dataset, please contact:
- **Yufei Wei**: [email]
- **Yue Wang** (Corresponding author): wangyue@iipc.zju.edu.cn

## 📄 License

This dataset is released under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) license for academic use. For commercial use, please contact the authors.

## 🙏 Acknowledgments

This work was supported by:
- National Nature Science Foundation of China (Grant 62373322)
- Zhejiang Provincial Natural Science Foundation (Grant LD24F030001)
- Laboratory of Industrial Control and Technology, Zhejiang University

---

**Note**: The dataset will be continuously updated with additional sequences and improved annotations. Please check back for updates!
